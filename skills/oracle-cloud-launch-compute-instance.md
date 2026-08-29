---
name: oracle-cloud-launch-compute-instance
description: Launch, power-manage and terminate an Oracle Cloud Infrastructure compute instance safely, including the reversibility caveats around termination.
api: Oracle Cloud Infrastructure Core Services API
spec: openapi/_original/oracle-cloud-core-services-openapi.yaml
host: https://iaas.{region}.oraclecloud.com/20160918
operations:
  - ListAvailabilityDomains
  - ListImages
  - ListShapes
  - ListSubnets
  - LaunchInstance
  - GetInstance
  - InstanceAction
  - TerminateInstance
generated: '2026-08-29'
method: generated
source: openapi/_original/, conventions/oracle-cloud-conventions.yml, errors/oracle-cloud-problem-types.yml
---

# Launch a compute instance on OCI

Every operation below was verified present in Oracle's own contract. `ListAvailabilityDomains`
lives on the Identity API (`identity.{region}.oraclecloud.com/20160918`); the rest are on the Core
Services API.

## Before you call anything

- Sign every request. There is no bearer token — OCI uses an RSA API signing key
  (tenancy/user/fingerprint) or instance/resource principals.
- You need a `compartmentId` (an OCID). Almost every call requires it.
- Send `opc-retry-token` on `LaunchInstance`. It is accepted, it expires after 24 hours, and it is
  the only thing standing between a timeout and a duplicate instance you pay for.

## Steps

1. `ListAvailabilityDomains` (Identity API) with `compartmentId` = your tenancy OCID. Pick an AD name.
2. `ListImages` with `compartmentId`, filtering by `operatingSystem` and `shape`. Take `id`.
3. `ListShapes` with `compartmentId` and `availabilityDomain`. Confirm the shape is offered there —
   a shape valid in one AD may not exist in another.
4. `ListSubnets` with `compartmentId` and `vcnId`. You need a subnet OCID in the same AD (or a
   regional subnet). If you have no VCN yet, run the `oracle-cloud-provision-vcn-network` skill first.
5. `LaunchInstance` with `compartmentId`, `availabilityDomain`, `shape`, `sourceDetails` (image OCID),
   `createVnicDetails.subnetId`, and `opc-retry-token`.
   The response is `202` with an `opc-work-request-id`; the instance starts in `PROVISIONING`.
6. Poll `GetInstance` until `lifecycleState` is `RUNNING`. Capture the `etag` — you need it for any
   later `if-match` update.
7. Power actions go through `InstanceAction` with `action` = `START`, `STOP`, `RESET`, `SOFTSTOP`,
   `SOFTRESET`. Oracle warns that `SOFTSTOP` waits 15 minutes for the OS before forcing power off.

## Reversibility — read this before step 8

`TerminateInstance` is described in Oracle's own contract as "Permanently terminates (deletes) the
specified instance." **There is no undo and no grace window.**

- `preserveBootVolume=true` keeps the boot volume after termination. It does not restore the instance;
  it lets you launch a new one from the retained volume.
- `preserveDataVolumes` defaults to true — data volumes survive unless you explicitly say false.
- If the intent is "stop paying for a while", use `InstanceAction` with `STOP`, not `TerminateInstance`.

## Errors you will actually hit

| Status | Code | What to do |
|---|---|---|
| 400 | `LimitExceeded` | Tenancy service limit for this shape. Request an increase; do not retry. |
| 400 | `QuotaExceeded` | Compartment quota set by an admin. Do not retry. |
| 401 | `NotAuthenticated` | Signature or key id is wrong. Do not retry. |
| 404 | `NotAuthorizedOrNotFound` | OCID wrong OR you lack the policy. These are deliberately indistinguishable. |
| 409 | `IncorrectState` | The instance is mid-transition. Retry with back-off. |
| 409 | `InvalidatedRetryToken` | Your retry token was consumed and then invalidated. Mint a new one and re-read state first. |
| 412 | `NoEtagMatch` | Re-read the instance and retry with the current `etag`. |
| 429 | `TooManyRequests` | Back off exponentially, a few seconds up to 60. No Retry-After header is sent. |

Every response carries `opc-request-id`. Log it — it is what Oracle Support asks for.
