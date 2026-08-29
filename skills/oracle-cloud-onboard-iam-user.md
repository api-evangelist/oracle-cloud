---
name: oracle-cloud-onboard-iam-user
description: Onboard a user into an OCI tenancy — compartment, group, policy, user, API signing key — and understand what can and cannot be undone.
api: Oracle Cloud Infrastructure Identity and Access Management Service API
spec: openapi/_original/oracle-cloud-identity-openapi.yaml
host: https://identity.{region}.oraclecloud.com/20160918
operations:
  - ListCompartments
  - CreateCompartment
  - CreateGroup
  - CreateUser
  - AddUserToGroup
  - CreatePolicy
  - UploadApiKey
  - ListUsers
  - ListPolicies
  - RemoveUserFromGroup
  - DeleteUser
  - RecoverCompartment
generated: '2026-08-29'
method: generated
source: openapi/_original/oracle-cloud-identity-openapi.yaml, conventions/oracle-cloud-conventions.yml
---

# Onboard a user into an OCI tenancy

IAM calls must go to the **home region** of the tenancy. Sending a write to any other region returns
403 `NotAllowed` — "This operation must be directed at the home region."

## Steps

1. `ListCompartments` with `compartmentId` = tenancy OCID, `compartmentIdInSubtree: true` to see the
   tree. `CreateCompartment` if the target does not exist. Send `opc-retry-token` on the create.
2. `CreateGroup` with `compartmentId` = tenancy OCID (groups are tenancy-level, not compartment-level),
   `name`, `description`.
3. `CreateUser` with `compartmentId` = tenancy OCID, `name`, `description`, optionally `email`.
4. `AddUserToGroup` with `userId` and `groupId`.
5. `CreatePolicy` with `compartmentId`, `name`, and `statements` — plain-language rules, e.g.
   `Allow group Developers to manage instance-family in compartment Dev`. Policies are the whole of
   OCI authorization; there are no roles.
6. `UploadApiKey` with `userId` and the PEM public key so the user can sign API requests.
   **Never post a private key to this API.** The response returns the key `fingerprint`, which the
   user pairs with the tenancy and user OCIDs to form their key id.

## Reversibility

- `RecoverCompartment` (`POST /compartments/{compartmentId}/actions/recoverCompartment`) moves a
  compartment from `DELETED` back to `ACTIVE`. Oracle's contract states the capability but **states
  no window** — do not promise a customer a number this API does not publish.
- `DeleteCompartment` requires the compartment to be empty.
- `RemoveUserFromGroup` reverses step 4 cleanly. `DeleteUser` does not restore anything the user did.
- Deleting an API key revokes signing immediately; there is no grace period.

## Conventions

- 44 operations in this contract accept `opc-retry-token` (24-hour expiry) — use it on every create.
- 57 accept `if-match` with the resource `etag`; a stale etag returns 412 `NoEtagMatch`.
- 404 `NotAuthorizedOrNotFound` deliberately conflates "does not exist" with "you are not allowed to
  see it". When onboarding, assume the policy is missing before assuming the OCID is wrong.
