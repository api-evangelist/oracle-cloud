---
name: oracle-cloud-provision-vcn-network
description: Build a routable OCI virtual cloud network — VCN, internet gateway, route table, security list, subnet — and tear it down in the right order.
api: Oracle Cloud Infrastructure Core Services API
spec: openapi/_original/oracle-cloud-core-services-openapi.yaml
host: https://iaas.{region}.oraclecloud.com/20160918
operations:
  - CreateVcn
  - GetVcn
  - ListVcns
  - CreateInternetGateway
  - CreateRouteTable
  - UpdateRouteTable
  - CreateSecurityList
  - CreateSubnet
  - ListSubnets
  - DeleteSubnet
  - DeleteVcn
generated: '2026-08-29'
method: generated
source: openapi/_original/oracle-cloud-core-services-openapi.yaml, conventions/oracle-cloud-conventions.yml
---

# Provision an OCI virtual cloud network

Networking resources form a dependency chain, and OCI enforces it on delete as strictly as on
create. Build in this order; tear down in exactly the reverse.

## Build

1. `CreateVcn` with `compartmentId`, `cidrBlocks`, `displayName`, `dnsLabel`. Send `opc-retry-token`.
   A VCN is created with a default route table, default security list and default DHCP options —
   note their OCIDs from `GetVcn`; you can configure those instead of creating new ones.
2. `CreateInternetGateway` with `vcnId`, `isEnabled: true`. Skip for a private-only network.
3. `CreateRouteTable` with `vcnId` and a rule `{destination: "0.0.0.0/0", destinationType:
   "CIDR_BLOCK", networkEntityId: <internet gateway OCID>}`. Or `UpdateRouteTable` on the VCN's
   default route table instead of creating a second one.
4. `CreateSecurityList` with `vcnId`, `ingressSecurityRules`, `egressSecurityRules`. Egress is
   deny-by-default in a new list — an empty egress list means nothing gets out.
5. `CreateSubnet` with `vcnId`, `cidrBlock` (must sit inside the VCN CIDR), `routeTableId`,
   `securityListIds`, and either `availabilityDomain` (AD-specific) or nothing (regional subnet —
   prefer this). Set `prohibitPublicIpOnVnic: true` for a private subnet.

## Verify

- `ListSubnets` with `compartmentId` and `vcnId`; poll until `lifecycleState` is `AVAILABLE`.
- Every list operation here pages with `limit` + `page` and the `opc-next-page` response header.
  **Stop when the header is absent, not when the array is empty** — Oracle states a page can be
  empty while more results remain.

## Tear down

Reverse order, and each step must complete before the next:

1. Terminate every instance whose VNIC is in the subnet (see `oracle-cloud-launch-compute-instance`).
2. `DeleteSubnet` — fails with 409 `IncorrectState` while any VNIC is still attached. Retry with
   back-off; the VNIC detach is asynchronous after instance termination.
3. Delete the route table, security list and internet gateway you created (defaults cannot be deleted).
4. `DeleteVcn` — fails while any child resource remains.

## Reversibility

There is none. No network delete in this contract has a recover operation or a retention window.
`DeleteVcn` and `DeleteSubnet` are immediate and permanent. If you need a rollback, capture the
create payloads before you delete, or manage the network through Resource Manager (Terraform),
where a plan can be re-applied.

## Errors

- 409 `IncorrectState` — a dependent resource is still attaching or detaching. Retry with back-off.
- 409 `Conflict` — a genuine, non-transient conflict (e.g. overlapping CIDR). Do not retry.
- 400 `LimitExceeded` — VCN or subnet limit for the tenancy.
- 412 `NoEtagMatch` — re-read and retry with the current `etag`.
