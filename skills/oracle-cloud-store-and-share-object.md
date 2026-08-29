---
name: oracle-cloud-store-and-share-object
description: Put an object into OCI Object Storage, share it with a time-boxed pre-authenticated request, and restore it from Archive — the one OCI flow with a numerically stated reversal window.
api: Oracle Cloud Infrastructure Object Storage Service API
spec: openapi/_original/oracle-cloud-object-storage-openapi.yaml
host: https://objectstorage.{region}.oraclecloud.com
operations:
  - GetNamespace
  - CreateBucket
  - PutObject
  - GetObject
  - HeadObject
  - ListObjects
  - CreatePreauthenticatedRequest
  - ListPreauthenticatedRequests
  - DeletePreauthenticatedRequest
  - RestoreObjects
  - DeleteObject
generated: '2026-08-29'
method: generated
source: openapi/_original/oracle-cloud-object-storage-openapi.yaml, conventions/oracle-cloud-conventions.yml
---

# Store and share an object on OCI Object Storage

Object Storage is the one OCI service served at the root path — there is no `/YYYYMMDD` version
segment. It is also the service where the pagination rule differs from every other OCI API.

## Steps

1. `GetNamespace` — returns your tenancy's Object Storage namespace string. Every subsequent path is
   `/n/{namespaceName}/b/{bucketName}/...`. Cache it; it never changes.
2. `CreateBucket` with `compartmentId`, `name`, and optionally `versioning: Enabled`.
   **Turn versioning on if you care about recovering deleted objects** — see Reversibility.
3. `PutObject` — the body is the object bytes. Send `if-none-match: *` to make the write
   create-only, or `if-match: <etag>` to make it a safe overwrite.
4. `HeadObject` to check existence and read the `etag` without transferring the body.
5. `ListObjects` — **this operation does not use `opc-next-page`.** It returns `nextStartWith` in the
   response *body*, and you page with the `start` query parameter. Every other OCI list operation
   works the other way. Getting this wrong is the single most common OCI pagination bug.
6. `CreatePreauthenticatedRequest` to share without credentials: set `accessType`
   (`ObjectRead`, `ObjectWrite`, `ObjectReadWrite`, `AnyObjectRead`, ...) and `timeExpires`.
   **The full PAR URL is returned exactly once, in the create response. It is never retrievable
   again** — `ListPreauthenticatedRequests` returns metadata only. Capture it or you must re-create.
7. `DeletePreauthenticatedRequest` revokes the share immediately.

## Reversibility

- **Archive restore has a stated window.** `RestoreObjects` restores an object from the Archive tier
  for **24 hours by default**; the `hours` field accepts **1 to 240** (10 days). This is the only
  reversal window Oracle states numerically inside a contract.
- **Delete is recoverable only with versioning on.** With versioning enabled a `DeleteObject` writes
  a delete marker and prior versions stay addressable by `versionId` via `ListObjectVersions`.
  With versioning off, the delete is final. Oracle publishes no retention window either way.
- `DeleteBucket` requires the bucket to be empty.

## Conventions that apply here

- `opc-retry-token` is **not** attached to any operation in this contract — do not assume replay
  protection on `PutObject`. Use `if-none-match: *` / `if-match` for safety instead.
- `if-match` / `etag` is available on 20 operations here; 412 `NoEtagMatch` on conflict.
- Errors are `{"code","message"}`. Object Storage adds `304`, `408`, `411` to the usual set.
