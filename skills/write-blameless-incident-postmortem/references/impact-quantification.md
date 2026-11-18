# Customer impact quantification

Open this during Step 4. Show every formula with inputs. Label estimates.

## Required impact fields
| Field | How to derive | If missing |
|---|---|---|
| Impact window | Impact start to impact end from SLI data | Use alert/rollback times; label `estimate` |
| Duration | end - start | - |
| Affected surface | Endpoints, features, regions, plans | Ask service owner |
| Affected tenants/accounts | Distinct tenant IDs with >=1 failed request (logs/APM), or tenants in affected shard/region | `[GAP]`; give upper bound = tenants in affected scope |
| % of active tenants | affected / active tenants in same period | `[GAP]` |
| Affected end users | Distinct user IDs with failures | Often unknowable; say so |
| Failed requests | sum of bad events in window | error rate x total requests (estimate) |
| Peak / average error rate | From metrics | - |
| Latency impact | p50/p95/p99 vs baseline | - |
| Data loss / corruption | yes / no / unknown + evidence | Must not be left blank; say unknown |
| Support tickets | Count tagged to incident | Ask support lead |
| Revenue/transaction impact | Failed checkouts, payments, jobs | Only if user supplies data |
| Status page | First post time, components marked | - |

## SLO error-budget burn
Request-based SLO:
- Allowed bad events in window = total eligible events in SLO window x (1 - SLO target)
- Burn % = incident bad events / allowed bad events x 100

Time-based SLO:
- Budget minutes = window minutes x (1 - SLO target). Example: 30 days x 1,440 = 43,200 min; at 99.9% budget = 43.2 min.
- Burn % = bad minutes / budget minutes x 100. Define a bad minute per the org's SLI definition (e.g. error rate above threshold); ask if unclear.

Burn rate during the incident (for alert tuning findings):
- Burn rate = observed error rate / (1 - SLO target). Example: 6% errors on a 99.9% SLO = 0.06 / 0.001 = 60x.

Also report remaining budget for the window if the user gives prior consumption, and whether the team's error-budget policy (e.g. feature freeze) is now triggered - per their policy, not yours.

## SLA (contractual)
- SLAs are contract terms; definitions (measurement window, exclusions, maintenance, scheduled downtime, per-region) vary by customer and plan.
- Output only: `Impact window may count toward SLA availability for <plans/customers>. Verify contractual SLA definition, exclusions and credit terms with account management/legal.`
- Do not compute credits or state a breach occurred.

## Customer impact summary (max 3 sentences)
Pattern: what customers experienced, when (UTC), how many/what share, current state. No internal cause jargon, no blame, no promises of dates.
Example: `Between 14:02 and 14:44 UTC on 10 Nov 2026, about 6% of payment requests failed with errors for roughly 11% of customer accounts. No payment data was lost or altered. Service is fully restored and we are adding safeguards to prevent recurrence.`
Only state `no data was lost` if evidence supports it.

## Severity check
Compare quantified impact with the org's SEV definitions and note if the declared severity should be revised up or down; the user decides.
