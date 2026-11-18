---
name: write-blameless-incident-postmortem
description: "Drafts blameless incident postmortems (post-incident reviews, PIRs, RCAs) for SaaS engineering teams from user-supplied exports: PagerDuty/Opsgenie paging history, Datadog/Prometheus/Grafana alerts, deploy and change logs, Slack/Teams incident-channel transcripts. Builds a UTC timeline with detection/mitigation metrics, separates trigger from contributing factors and root cause, quantifies customer impact (tenants, duration, error rate, SLO error-budget burn, SLA exposure, support tickets) and turns findings into owned, dated, prioritized action items. Use when a user says 'write the postmortem', 'draft the PIR/RCA for this SEV-1', 'turn this incident channel into a timeline', 'how much error budget did we burn', 'what was the root cause vs trigger', or 'make this postmortem blameless'."
metadata:
  generated_by: "skill-factory"
  generated_at: "2026-11-18"
  industry: "saas"
  region: "global"
  subniche: "incident-postmortem-writing"
  role: "devops"
  notice: "Machine-generated. Review before use in regulated work."
---

# Write a blameless incident postmortem

## Guardrails (read first)
- Work only from exports and facts the user pastes or attaches. Never claim to have queried Datadog, Grafana, PagerDuty, Sentry, CloudWatch or any live system.
- Do not run or coordinate live response, page anyone, or advise mid-incident beyond telling the user to follow their incident process.
- Never assign blame or make performance judgments. If asked who caused it, answer with the system conditions that allowed the action to cause harm.
- Do not draft breach notifications, regulator filings, contractual SLA-credit letters or full status-page posts. Write at most a 3-sentence customer impact summary.
- If inputs suggest unauthorized access to, or exposure of, personal or customer data: add a top-of-document flag `ESCALATE: possible data exposure - route to security/privacy/legal` and do not characterize notification obligations.

## Step 1 - Collect inputs
Ask for whatever is missing, in one message:
1. Incident ID, severity (and the org's SEV definitions), affected services/regions.
2. Paging history export (PagerDuty/Opsgenie/incident.io/FireHydrant): triggered, acknowledged, escalated, resolved times.
3. Alert/monitor history with metric names and thresholds.
4. Deploy, feature-flag and config-change log for the 24 h before impact (CI/CD, Argo CD, Spinnaker, LaunchDarkly, Terraform applies).
5. Incident-channel transcript (Slack/Teams), with the export's timezone.
6. Impact data: error rate / latency graphs or numbers, request counts, affected tenants or users, support ticket count, status-page entries.
7. SLO definitions (SLI, target, window) and whether any customer SLAs apply.
8. House conventions: template, naming policy (names vs roles; default to roles), action-item tracker (Jira/Linear), due-date norms.

Minimum to start: a transcript or paging log plus one impact signal. Otherwise draft anyway with `[GAP: ...]` markers and a list of questions.

## Step 2 - Normalize and build the timeline
Open `references/timeline-reconstruction.md`.
- Convert every timestamp to UTC, `YYYY-MM-DD HH:MM:SS UTC`. Confirm each export's source timezone; never assume. Note clock source per row.
- One event per row: time, event, source, actor role. Merge duplicates; keep the earliest reliable time.
- Mark milestones: change introduced, impact start, first alert, page, ack, IC declared, diagnosis, mitigation applied, impact end, all-clear.
- Compute time to detect (impact start -> first alert/report), time to acknowledge, time to mitigate (impact start -> impact end), time to resolve. State which definition you used.
- If impact start precedes the first alert, say so explicitly; detection gaps are findings.

## Step 3 - Separate trigger, contributing factors, root cause
Open `references/causal-analysis.md`.
- Trigger: the event that started impact (a deploy, traffic spike, cert expiry, dependency outage).
- Contributing factors: conditions that widened blast radius, delayed detection or slowed recovery.
- Root cause(s): the systemic gap that let the trigger cause customer harm. Usually a missing guardrail, validation, isolation or feedback loop. Plural is fine.
- Reject `human error`, `operator mistake`, `didn't follow the runbook` as root causes; ask why the system made that action possible and likely.
- Mark each causal claim `confirmed` (evidence cited) or `hypothesis` (needs verification).

## Step 4 - Quantify customer impact
Open `references/impact-quantification.md`.
- Report: impact window, affected surface (endpoints/features/regions), affected tenants/users (count and % of active), peak and average error rate or latency, failed requests, data loss/corruption (yes/no/unknown), support tickets, SLO error-budget consumed (% of window budget).
- Show the formula and inputs for every derived number. Label estimates as estimates with their method.
- SLA: state only whether the window may intersect SLA terms and flag `verify contractual SLA definition and credit terms with account/legal`. Never compute credits as fact.

## Step 5 - Learnings
List what went well, what went poorly, and where we got lucky (e.g. low-traffic hour, the one engineer who knew the legacy system was online). Lucky items are hidden risk; each should feed an action item or an explicit accepted-risk note.

## Step 6 - Action items
Open `references/action-items.md`.
- Each item: ID, action (verb + specific object + done-criterion), type (prevent / detect / mitigate / process), owner (named person or team as the user specifies; use `[OWNER: TBD]` if unknown), due date (ISO), priority (P0-P3 or house scale), tracking ticket.
- Map every root cause and contributing factor to at least one item; map every item back to a finding.
- No vague items (`improve monitoring`, `be more careful`, `add more tests`). No item owned by `everyone`.

## Step 7 - Blameless language pass
Open `references/blameless-language.md` and rewrite every sentence that names a person as the subject of a failure, uses hindsight words (`should have`, `obviously`, `failed to`, `careless`), or speculates about intent. Replace names with roles unless the house policy says otherwise.

## Step 8 - Assemble
Use `references/postmortem-template.md`. Output, in order: title block, summary (5 lines max), customer impact summary (3 sentences max), impact metrics table, timeline table, causal analysis, learnings, action items table, open questions/`[GAP]` list, appendix of sources. Default format: Markdown suitable for Confluence/Notion/Google Docs paste.

## Missing or conflicting information
- Missing: write `[GAP: what is missing - who can supply it]`. Never invent timestamps, counts or owners.
- Conflicting timestamps across sources: keep both, note the delta, prefer paging/monitoring system clocks over chat message times for machine events and chat times for human decisions.
- Unverified cause: keep it in `hypothesis` status and add a verification action item.
- Ambiguous severity: report what the SEV definitions imply and ask the user to confirm.

## Worked example
Input (abridged): Slack export in US/Pacific; PagerDuty in UTC. `06:02 PST deploy bot: payments-api v4.18.2 config-only to prod (all regions)`. Datadog monitor `payments-api 5xx > 5% (5m avg)` triggered 14:09:30 UTC. PagerDuty ack 14:11:05 UTC by on-call SRE. `06:31 PST IC: rolling back config`. Rollback complete 14:38 UTC; 5xx back to baseline 14:44 UTC. Logs: DB connection pool max changed 200 -> 20. 2.3M requests in window, 138,000 returned 5xx. 212 of 1,900 active tenants hit errors. 41 support tickets. SLO: 99.9% request availability, 30-day rolling, 120M requests in window.

Expected output shape (excerpt):

```
Summary: For 42 minutes (14:02-14:44 UTC, 2026-11-10) payments-api returned HTTP 5xx on ~6% of requests after a config-only deploy reduced the DB connection pool from 200 to 20. Rollback restored service.

| Time (UTC) | Event | Source | Actor |
| 14:02:00 | payments-api v4.18.2 config deploy to all regions; impact begins | deploy bot (Slack, converted from PST) | CI/CD |
| 14:09:30 | Monitor 'payments-api 5xx > 5%' triggers | Datadog | system |
| 14:11:05 | Page acknowledged | PagerDuty | on-call SRE |
| 14:31:00 | Decision to roll back config | Slack | IC |
| 14:44:00 | 5xx at baseline; impact ends | Datadog | system |
TTD 7m30s | TTA 1m35s after alert | TTM 42m

Trigger: config deploy lowering pool max to 20 (confirmed: config diff).
Contributing: config-only deploys skip canary; 5m-avg monitor delayed detection ~7m; runbook lacked config-rollback steps.
Root cause: config changes reach all prod regions with no validation or progressive rollout (confirmed: pipeline definition).

Impact: 138,000 failed requests / 2.3M (6.0%); 212 of 1,900 tenants (11.2%); 41 tickets.
Error budget: 120M x 0.001 = 120,000 allowed bad requests; 138,000 / 120,000 = 115% of 30-day budget (exhausted).
SLA: [verify contractual SLA definition and credit terms with account/legal]

| ID | Action | Type | Owner | Due | Priority | Ticket |
| AI-1 | Route config-only deploys through the canary stage with automated 5xx rollback gate | prevent | Platform team | 2026-12-05 | P0 | [GAP] |
| AI-2 | Add schema bounds check rejecting pool max < 100 for payments-api | prevent | Payments team | 2026-11-28 | P1 | [GAP] |
| AI-3 | Add 1m multi-window burn-rate alert on payments-api availability SLO | detect | SRE | 2026-12-01 | P1 | [GAP] |
```

## Final check before returning
- Every number traces to an input or a shown formula; every timestamp is UTC with a source.
- Trigger, contributing factors and root cause are distinct; none is `human error`.
- Every finding has an action item; every action item has owner, ISO due date, priority.
- No individual is blamed; hindsight language removed.
- All gaps, hypotheses and legal/SLA flags are listed in Open questions.
