# Causal analysis: trigger, contributing factors, root cause

Open this during Step 3.

## Definitions
- Trigger: the proximate event that started impact. Answers: what changed right before it broke?
- Contributing factors: conditions without which impact would have been smaller, shorter or detected sooner. Categories: blast radius, detection, diagnosis, mitigation, communication.
- Root cause(s): the systemic condition(s) that made the trigger able to cause customer harm. Fixing a root cause prevents a class of incidents, not just this exact one.

Test: if you only fix the trigger (revert the bad config), could a similar change cause the same outage next week? If yes, you have not reached the root cause.

## Methods
1. Five whys, branching. Ask why at each level but allow multiple branches; linear five-whys hides parallel causes. Stop when the answer is a design, process or organizational condition the team can change.
2. Causal tree. Draw impact at top; children are necessary conditions. Each leaf needs evidence or a `hypothesis` tag.
3. Contributing-factor sweep. For each category ask:
   - Blast radius: why did it affect all regions/tenants rather than a cell, shard or canary?
   - Detection: why did the alert fire when it did? Was the SLI customer-facing? Evaluation window?
   - Diagnosis: what evidence was missing or misleading? Dashboards, logs, traces, runbooks?
   - Mitigation: was rollback fast and known? Feature flags? Was the rollback path tested?
   - Communication: when were status page, support and affected customers informed?

## Common SaaS trigger / root-cause pairs
| Trigger | Typical root-cause class |
|---|---|
| Config change or feature flag toggle | Config/flags bypass progressive rollout, validation or review |
| Schema migration lock | No online-migration tooling or migration review gate |
| Expired TLS cert or secret | No automated renewal or expiry alerting |
| Noisy-neighbor tenant | Missing per-tenant rate limits or isolation |
| Dependency outage (cloud, payment, auth provider) | No timeout/circuit breaker/fallback; single-region or single-vendor dependency |
| Traffic spike | Autoscaling limits, missing load shedding, untested capacity |
| Retry storm | Retries without backoff/jitter or budgets |
| Disk/quotas full | No capacity forecasting or alerting on saturation |

These are prompts, not conclusions; confirm with evidence.

## Rules
- `Human error` is never a root cause. Restate as the condition: `the CLI accepts production targets without confirmation`, `the runbook step was ambiguous`, `the deploy UI does not show region scope`.
- Avoid counterfactual blame (`if X had checked...`). Use: `the process did not include a check for...`.
- Distinguish confirmed vs hypothesis. Each hypothesis gets a verification action item.
- Multiple root causes are normal. Do not force a single cause.
- Note what is out of the team's control (vendor outage) but still identify the team-controlled resilience gap.

## Output format
```
### Trigger
<one sentence> (confirmed: <evidence>)
### Contributing factors
- [blast radius] ... (confirmed/hypothesis: <evidence>)
- [detection] ...
### Root cause(s)
1. ... (confirmed/hypothesis: <evidence>)
### Causal chain
Root cause -> enabled trigger -> impact; contributing factors -> widened/prolonged
```
