# Postmortem template

Use this in Step 8 unless the user supplies a house template; if they do, map these sections into theirs and keep all required content.

```markdown
# Postmortem: <short descriptive title> (<INCIDENT-ID>)

| Field | Value |
|---|---|
| Status | Draft / In review / Final |
| Severity | SEV-<n> (per <org> definitions) |
| Incident date | YYYY-MM-DD |
| Impact window | HH:MM-HH:MM UTC (<duration>) |
| Services / regions | ... |
| Incident commander | <role or name per policy> |
| Author(s) | ... |
| Review meeting | <date or [GAP]> |

<!-- If applicable: ESCALATE: possible data exposure - route to security/privacy/legal -->

## Summary
<= 5 lines: what happened, impact, trigger, mitigation, key follow-up.

## Customer impact summary
<= 3 sentences, plain language.

## Impact metrics
| Metric | Value | Method / source |
|---|---|---|
| Duration | | |
| Affected tenants | n of N (x%) | |
| Failed requests / error rate (peak, avg) | | |
| Latency (p95/p99 vs baseline) | | |
| Data loss / corruption | yes / no / unknown | |
| Support tickets | | |
| SLO error budget consumed | x% of <window> budget | formula |
| SLA | verify with account/legal | |

## Timeline (UTC)
| Time | Event | Source | Actor |
|---|---|---|---|

TTD: | TTA: | TTM: | TTR: (definitions used: ...)

## Causal analysis
### Trigger
### Contributing factors
### Root cause(s)
### Causal chain

## Learnings
### What went well
### What went poorly
### Where we got lucky

## Action items
| ID | Action | Type | Linked finding | Owner | Due | Priority | Ticket |
|---|---|---|---|---|---|---|---|

## Open questions and gaps
- [GAP: ...] - who can answer
- Hypotheses awaiting verification

## Appendix: sources
- Paging export: <tool, timezone>
- Alerts: <monitor names>
- Deploy/change log: <system>
- Chat: <channel, export timezone>
- Dashboards/graphs referenced
```

## Review readiness
Before marking `In review`: all [GAP] items either filled or assigned to a person; all action items have owners and dates; blameless pass complete; a responder not involved in authoring has checked the timeline for accuracy.
