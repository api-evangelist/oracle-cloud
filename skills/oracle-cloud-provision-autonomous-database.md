---
name: oracle-cloud-provision-autonomous-database
description: Provision, connect to, stop/start and point-in-time restore an OCI Autonomous Database.
api: Oracle Cloud Infrastructure Database Service API
spec: openapi/_original/oracle-cloud-database-openapi.yaml
host: https://database.{region}.oraclecloud.com/20160918
operations:
  - CreateAutonomousDatabase
  - GetAutonomousDatabase
  - ListAutonomousDatabases
  - GenerateAutonomousDatabaseWallet
  - StopAutonomousDatabase
  - StartAutonomousDatabase
  - RestartAutonomousDatabase
  - RestoreAutonomousDatabase
  - DeleteAutonomousDatabase
generated: '2026-08-29'
method: generated
source: openapi/_original/oracle-cloud-database-openapi.yaml, conventions/oracle-cloud-conventions.yml
---

# Provision an OCI Autonomous Database

The Database Service contract is the largest in OCI — 444 operations — and the most
idempotency-aware: 160 of them accept `opc-retry-token`. Use it on every create. A duplicated
database is an expensive mistake.

## Steps

1. `CreateAutonomousDatabase` with `compartmentId`, `dbName`, `dbWorkload`
   (`OLTP` / `DW` / `AJD` / `APEX`), `computeCount` or `cpuCoreCount`, `dataStorageSizeInTBs`,
   `adminPassword`, and `opc-retry-token`.
   - Note: `cpuCoreCount` was deprecated on 2025-05-28 with support ending 2026-05-28
     (see `lifecycle/oracle-cloud-lifecycle.yml`). Use `computeCount` on new integrations.
   - `isFreeTier: true` provisions an Always Free instance.
2. Poll `GetAutonomousDatabase` until `lifecycleState` is `AVAILABLE`. Capture the `etag`.
3. `GenerateAutonomousDatabaseWallet` returns the mTLS connection wallet as a binary body.
   **Treat the response as a secret** — never log it, never write it into an artifact.
   `isMTLSConnectionRequired` has a service-side default that Oracle changed on 2023-07-01; read
   the current value from the resource rather than assuming.
4. `StopAutonomousDatabase` / `StartAutonomousDatabase` stop billing for compute while retaining
   storage. `RestartAutonomousDatabase` bounces it in place.

## Reversibility

- `RestoreAutonomousDatabase` (`POST /autonomousDatabases/{id}/actions/restore`) does a point-in-time
  restore from automatic backups. The reachable window is whatever backup retention is configured on
  the database — **Oracle's contract states no universal number, so do not assert one.** Read the
  retention from the resource before promising a recovery point.
- `DeleteAutonomousDatabase` publishes no recovery operation. If you need an escape hatch, take a
  manual backup or a clone first (`CreateAutonomousDatabaseBackup`, `ListAutonomousDatabaseClones`).
- Stop is fully reversible with Start; it is the correct answer to "pause this".

## Errors

- 400 `LimitExceeded` / `QuotaExceeded` — tenancy limit or compartment quota on ADB compute or storage.
- 409 `IncorrectState` — the database is mid-lifecycle. Retry with back-off.
- 409 `InvalidatedRetryToken` — the token was consumed then invalidated. Re-read state before re-firing.
- 429 `TooManyRequests` — back off exponentially up to 60 seconds. No Retry-After header is sent.
