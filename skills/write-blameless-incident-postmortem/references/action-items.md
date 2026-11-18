# Action items

Open this during Step 6.

## Required fields
| Field | Rule |
|---|---|
| ID | AI-1, AI-2 ... or tracker key |
| Action | Verb + specific object + done-criterion. Testable by someone who was not in the incident. |
| Type | prevent (stop recurrence), detect (find it sooner), mitigate (reduce blast radius / speed recovery), process (runbooks, comms, training, on-call) |
| Linked finding | Root cause / contributing factor / lucky item it addresses |
| Owner | One named person or one team, as the user specifies. Never `everyone`, `eng`, `TBD` without a GAP marker. |
| Due date | ISO date. If user gives no norm, propose: P0 within 1-2 weeks, P1 within 30 days, P2 within a quarter, and label as proposed. |
| Priority | Org scale; default P0-P3 |
| Ticket | Jira/Linear key or `[GAP: create ticket]` |

## Priority guide (adjust to house policy)
- P0: addresses a confirmed root cause where recurrence is likely and impact is SEV-1/2 class.
- P1: major contributing factor (detection gap, missing rollback path) or root-cause verification.
- P2: diagnosis/communication improvements, runbook updates.
- P3: nice-to-have hardening, cleanup.

## Rewrite vague items
| Vague | Specific |
|---|---|
| Improve monitoring | Add multi-window burn-rate alert (1h and 5m) on checkout availability SLO paging the payments on-call |
| Add more tests | Add integration test that boots payments-api with production config bounds and fails CI if DB pool max < 100 |
| Be more careful with config | Require config-only deploys to pass the canary stage with automatic rollback when 5xx > 1% for 2 minutes |
| Update runbook | Add config rollback procedure with exact commands to payments-api runbook and link it from the alert body |
| Better communication | Post initial status-page update within the org's target after SEV-1/2 declaration; add template to IC checklist |

## Coverage rules
- Every root cause has at least one prevent item.
- Every detection-related contributing factor has a detect item.
- Every hypothesis has a verification item.
- Every `where we got lucky` entry has an item or an explicit accepted-risk statement with an approver role.
- Prefer fewer, high-leverage items; flag if more than ~10 items, as follow-through drops.
- Mark items completed during the incident as `done` with date, separate from open items.

## Table format
`| ID | Action | Type | Linked finding | Owner | Due | Priority | Ticket |`
