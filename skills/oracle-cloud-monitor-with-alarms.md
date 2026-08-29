---
name: oracle-cloud-monitor-with-alarms
description: Query OCI metrics, create an alarm, and wire it to a notification topic or a webhook endpoint.
api: Oracle Cloud Infrastructure Monitoring API and Notifications API
spec: openapi/_original/oracle-cloud-monitoring-openapi.yaml
host: https://telemetry.{region}.oraclecloud.com/20180401
operations:
  - ListMetrics
  - SummarizeMetricsData
  - CreateAlarm
  - GetAlarm
  - ListAlarms
  - UpdateAlarm
  - DeleteAlarm
  - GetAlarmHistory
  - CreateTopic
  - CreateSubscription
  - GetConfirmSubscription
generated: '2026-08-29'
method: generated
source: openapi/_original/oracle-cloud-monitoring-openapi.yaml, openapi/_original/oracle-cloud-notifications-openapi.yaml, asyncapi/oracle-cloud-events-webhooks.yml
---

# Monitor OCI resources with alarms

Two hosts are involved. Monitoring reads and alarms live on `telemetry.{region}.oraclecloud.com`;
metric *ingestion* (`PostMetricData`) goes to `telemetry-ingestion.{region}.oraclecloud.com`. Sending
a read to the ingestion host, or a write to the read host, fails.

## Steps

1. `ListMetrics` with `compartmentId` and a `namespace` (e.g. `oci_computeagent`, `oci_objectstorage`)
   to discover what is emitted and which dimensions exist.
2. `SummarizeMetricsData` with `namespace`, a `query` in MQL
   (e.g. `CpuUtilization[1m].mean()`), `startTime` and `endTime` (RFC 3339). This is the read path —
   it is a POST because the query goes in the body.
3. `CreateTopic` (Notifications API, `notification.{region}.oraclecloud.com/20181201`) with
   `compartmentId` and `name`.
4. `CreateSubscription` with `topicId`, `protocol` and `endpoint`.
   - `EMAIL` → an address. `HTTPS (Custom URL)` → your webhook URL, max 512 characters.
   - **The subscription starts in `PENDING` and delivers nothing until confirmed.** Oracle sends a
     confirmation to the endpoint; your webhook must call the confirmation URL, or use
     `ResendSubscriptionConfirmation` if it was missed. `GetConfirmSubscription` completes it.
5. `CreateAlarm` with `compartmentId`, `metricCompartmentId`, `namespace`, `query`, `severity`,
   `destinations: [<topic OCID>]`, `isEnabled: true`, and `pendingDuration` to suppress flapping.
6. `GetAlarmHistory` to see fired/reset transitions. `UpdateAlarm` with `if-match` to change it.

## Reversibility

- `UpdateAlarm` with `isEnabled: false` is the safe reversal — it stops delivery without losing the
  definition. Prefer it to `DeleteAlarm`, which is permanent and publishes no recovery path.
- `DeleteSubscription` stops delivery immediately; re-creating requires the confirmation handshake again.
- Only 3 of the 18 Monitoring operations accept `opc-retry-token`. Check the operation before relying
  on replay safety.

## Event shape

If you route to Events instead of Notifications, the payload is a **CloudEvents 0.1** envelope —
`cloudEventsVersion`, `eventID`, `eventType` (`com.oraclecloud.<service>.<action>`), `eventTime`,
plus a mandatory Oracle `extensions` object. A consumer written for CloudEvents 1.0
(`specversion`/`id`/`time`) will not parse it without a shim. See
`asyncapi/oracle-cloud-events-webhooks.yml`.
