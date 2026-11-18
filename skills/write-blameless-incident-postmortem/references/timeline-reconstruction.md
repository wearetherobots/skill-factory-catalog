# Timeline reconstruction

Open this during Step 2.

## Source reliability for timestamps
| Source | Good for | Watch out for |
|---|---|---|
| Monitoring (Datadog, Prometheus/Alertmanager, Grafana, CloudWatch, New Relic) | When a threshold was crossed; metric onset | Evaluation windows: a 5m-avg monitor fires minutes after onset. Back-date impact start from the metric graph, not the alert time. |
| Paging (PagerDuty, Opsgenie, incident.io, FireHydrant, Rootly) | Triggered, acked, escalated, resolved | Incident `resolved` is often clicked late; it is not impact end. Auto-resolve may fire early. |
| Deploy/change logs (GitHub Actions, GitLab CI, Jenkins, Argo CD, Spinnaker, Terraform, LaunchDarkly audit log) | When a change started and finished rolling out | Start vs finish of a rollout can differ by many minutes; record both for progressive rollouts. |
| Chat (Slack, Teams) | Human decisions, hypotheses, handoffs | Exports may be in the exporting user's local time or epoch seconds. Message time is when someone typed, not when they acted. |
| Status page (Statuspage, Instatus, etc.) | When customers were told | Posts lag impact; useful for communication-delay finding. |
| Support desk (Zendesk, Intercom, Salesforce) | First customer report | Ticket creation time vs customer-reported start time differ. |
| Cloud provider health dashboards | Upstream dependency events | Provider times may be rounded or posted retroactively. |

## Procedure
1. Inventory sources and record each source's timezone. Slack JSON exports use epoch `ts`; UI copy-paste uses viewer local time. If unknown, ask; if still unknown, mark `[GAP: timezone of <source>]` and do not convert.
2. Convert to UTC. Watch daylight-saving transitions; verify offset for the incident date, not today.
3. Extract candidate events: alerts, pages, acks, escalations, deploys, flag toggles, rollbacks, scaling actions, failovers, status posts, IC/role assignments, hypotheses stated, hypotheses ruled out, customer reports.
4. Deduplicate: one physical event reported by several sources becomes one row; cite all sources.
5. Order and look for gaps longer than ~10 minutes during active response. Gaps are often where diagnosis stalled; ask what happened.
6. Tag milestones (below).
7. Keep the timeline factual. Analysis goes in the causal section, not the event text.

## Milestones and metric definitions
State the definition used; orgs differ.
- Impact start: earliest point the customer-facing SLI degraded (from metric data), or the triggering change if metric data is absent (mark as estimate).
- Detection: first alert or first credible human/customer report, whichever is earlier. Note which.
- Acknowledgement: first human ack of the page.
- Mitigation: the action that stopped customer impact (rollback, failover, flag off, scale-out).
- Impact end: SLI back within normal bounds.
- Resolution: underlying issue fixed or risk removed (may be days later; note follow-up).

Durations:
- Time to detect (TTD) = detection - impact start
- Time to acknowledge (TTA) = ack - page triggered
- Time to mitigate (TTM) = impact end - impact start (some orgs use mitigation start; say which)
- Time to resolve (TTR) = resolution - impact start

Do not label these MTTx; MTT metrics are averages across incidents.

## Row format
`| YYYY-MM-DD HH:MM:SS UTC | Event (past tense, factual) | Source(s) | Actor role |`
Actor roles: system, CI/CD, on-call SRE, secondary on-call, IC, comms lead, service owner team, support, customer, vendor.

## Multi-day or multi-phase incidents
Split into phases (onset, partial mitigation, recurrence, full recovery) with a heading per phase and per-phase impact.
