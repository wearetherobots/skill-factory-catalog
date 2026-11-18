# Blameless language

Open this during Step 7. Blameless means: assume people acted reasonably given the information, tools and pressure they had. The document explains why the action made sense at the time and how the system allowed it to cause harm.

## Naming policy
- Default: roles, not names (on-call SRE, IC, service owner, deploying engineer).
- If the org's policy uses names in timelines, use them only as neutral actors of factual events, never as the subject of a failure.
- Never include names in the causal analysis or impact sections.

## Words and patterns to remove
- Hindsight/judgment: should have, failed to, neglected, obviously, simply, just, careless, sloppy, mistake by, fault, negligent, forgot.
- Intent speculation: didn't bother, ignored, rushed.
- Counterfactual blame: if X had only...
- Single-person root cause: X caused the outage.

## Rewrites
| Blameful | Blameless |
|---|---|
| Alex pushed a bad config that took down payments. | A config change reduced the DB connection pool from 200 to 20; the pipeline applied it to all regions without validation. |
| The on-call engineer ignored the alert for 20 minutes. | The alert was acknowledged at 14:11; mitigation began at 14:31. During this time responders investigated a database hypothesis because dashboards showed DB connection errors without showing the recent config change. |
| The engineer failed to follow the runbook. | The runbook did not cover config rollback, so responders reconstructed the steps during the incident. |
| Obviously the deploy should have been canaried. | Config-only deploys are not routed through the canary stage. |
| Support should have escalated sooner. | The first related ticket arrived at 14:15; the support-to-incident escalation path for that queue was not defined. |

## Explaining decisions (local rationality)
For each key human decision in the timeline, capture: what the person knew, what signals they saw, what options seemed available, and what made the chosen option reasonable. Source this from chat transcripts; if unclear, add `[GAP: ask responder what signals they were relying on]` rather than guessing.

## Requests that cross the line
If the user asks for a judgment on an individual, a performance note, or who to discipline: decline that part, explain that postmortems examine systems, and offer to list the system and process gaps instead.
