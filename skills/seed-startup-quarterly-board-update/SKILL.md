---
name: seed-startup-quarterly-board-update
description: "Drafts a candid quarterly board update for seed-stage startup founders from the metrics, financials and notes they provide. Produces a one-page summary covering MRR/revenue, growth, users and retention, cash, monthly burn and months of runway, wins and misses against last quarter's goals, top risks with mitigations, and specific asks of the board. Flags missing or inconsistent numbers. Use when a founder says 'write my board update', 'Q3 board deck pre-read', 'quarterly investor update for my board', 'how much runway do we have', 'turn these numbers into a board memo', or 'what should I ask my board for'. Does not build financial models, audit figures, draft board minutes or resolutions, give legal/tax/securities advice, or make pitch decks."
license: "CC-BY-4.0"
metadata:
  generated_by: "skill-factory"
  generated_at: "2026-11-25"
  industry: "finance"
  region: "global"
  subniche: "seed-stage-startup-governance"
  role: "founder"
  notice: "Machine-generated. Review before use in regulated work."
---

# Seed-stage quarterly board update

You draft the update a seed-stage founder sends to their board (typically 3 seats: founder(s) plus the lead investor, sometimes an independent and observers) as a pre-read before the quarterly meeting. The board's job is to spot problems early and help. Write so a director can read page one in three minutes and know: how much money is left, whether the plan is working, what is broken, and what the founder needs from them.

Core rules:
- Bad news goes on page one, not buried. "No surprises" is the standard.
- Every number has a period, a unit and a currency. No metric appears without its comparison (last quarter, plan, or target).
- Never fix, smooth or guess a founder's figures. Compute derived metrics from what they gave you and flag conflicts.
- Keep the one-pager to one page. Everything else goes to an appendix.

## Step 1 - Collect inputs

Ask for these in a single message. Accept spreadsheets, pasted exports (Stripe, QuickBooks/Xero, ChartMogul, Mixpanel/Amplitude), or rough notes.

Required:
1. Quarter covered and currency (e.g. Q3 2026, Jul 1 - Sep 30, USD).
2. Month-end bank cash for the last month of the prior quarter and each month of this quarter.
3. Monthly net burn for each month of the quarter (or cash in/out so you can compute it). Note any one-offs (annual prepayments, legal for financing, equipment, R&D tax credit receipts).
4. Last quarter's stated goals, verbatim, with their targets.
5. Core traction metric by month: MRR/revenue for revenue-stage; for pre-revenue, the leading indicator the board agreed on (pilots, LOIs, waitlist, design partners, activation).
6. Headcount at quarter start and end, plus open roles.

Useful but optional: customer/user counts, churn and expansion, retention cohorts, pipeline, gross margin, CAC, product milestones, fundraising status, last board meeting's action items, any committed but unreceived cash (SAFEs signed but unfunded, grants, venture debt).

If the founder cannot provide something, do not stall. Draft with a visible placeholder `[MISSING: what, why it matters]` and list it under "Questions for founder".

## Step 2 - Normalize

- Confirm quarter boundaries and that all monthly figures align to calendar or fiscal month-ends.
- Convert everything to one currency; state the rate and date if converted.
- Separate bank cash from committed-but-unreceived cash. Runway uses bank cash only; show committed cash as a separate line.
- Pick the business-model metric set (B2B SaaS, consumer, marketplace, pre-revenue) using `references/metrics-and-runway.md`.

## Step 3 - Compute derived metrics

Open `references/metrics-and-runway.md` for formulas and definitions. At minimum compute:
- Net burn per month and quarter total; gross burn if expenses are given.
- Runway in months = current bank cash / trailing-3-month average net burn. Also give the implied zero-cash month.
- QoQ growth of the core metric, and MoM for each month.
- Burn multiple (net burn / net new ARR) if revenue-stage.
- Retention (logo churn, NRR/GRR, or cohort retention) if data exists.

Show formulas in the appendix so directors can check them. Round runway to one decimal and money to the nearest thousand on page one.

## Step 4 - Run consistency checks

Run every check in the "Consistency checks" section of `references/metrics-and-runway.md`. The essentials:
- Opening cash - sum of net burn = closing cash? Gap above ~2% of quarterly burn gets flagged.
- MRR bridge: opening + new + expansion - contraction - churn = closing?
- Headcount change consistent with payroll change?
- Goals in this update match last quarter's wording and targets exactly?

List each issue under "Data issues" with the two conflicting numbers and the likely explanation to confirm. Do not resolve it yourself.

## Step 5 - Decide the headline (decision point)

Pick the opening line based on runway and trajectory:
- Runway < 6 months: lead with cash. Headline states months left, the zero-cash month and the plan (raise, cut, bridge). Add a dedicated "Cash plan" block and a decision ask.
- Runway 6-12 months: lead with the fundraising timeline. Founders commonly need to start a raise well before the last 6 months; state the planned start date and what metric must be true by then.
- Runway > 12 months: lead with the most important traction result, good or bad.
- If the core metric declined or missed plan by a wide margin, say so in the headline regardless of runway.

One sentence, numbers included. No adjectives like "great" or "tough".

## Step 6 - Score last quarter's goals

For each goal: status (Hit / Partial / Missed / Dropped), target vs actual, one-line cause, and what changes. Rules:
- Use the goal as originally written. If the founder wants to redefine it, show the original and note the change.
- "Dropped" requires a reason the board can evaluate (e.g. deprioritized after pricing test).
- Misses get a cause, not an excuse: name the controllable factor.
- Do not count unplanned wins as goal hits; list them separately under Wins.

## Step 7 - Risks and asks

Open `references/risks-and-asks.md` for categories, phrasing and good/bad examples.
- Risks: top 3-5, each with likelihood, impact, mitigation in progress, owner, and what would trigger escalation. Include at least one the board may not already know about.
- Asks: maximum 5, ranked. Each names the type (intro, hiring, advice, decision), a specific target or question, the director it is aimed at if known, and a by-when date.
- If an ask is a decision that legally requires board approval (financing, option grants, budget, officer changes), label it "Formal approval needed - counsel to prepare consent/resolution". You do not draft resolutions or advise on securities or tax.

## Step 8 - Next quarter goals

3-5 goals, each measurable with a number and a date, and tied to the next fundraise milestone where relevant. These become next quarter's scorecard, so word them exactly.

## Step 9 - Assemble

Use the layout in `references/update-template.md`. Return, in this order:
1. The one-page update.
2. Appendix: monthly table, metric definitions and formulas, MRR bridge, headcount, detailed notes.
3. "Data issues" - inconsistencies found in Step 4.
4. "Questions for founder" - missing inputs and judgment calls only they can make.

Tone: first person plural, plain, short sentences. Cut hype words, buzzwords and unexplained acronyms. If the update will also go to non-board investors (SAFE holders, angels), suggest a trimmed investor-update version and note that confidentiality and disclosure questions belong with counsel.

## Worked example

Input (founder notes, B2B SaaS, USD, Q3 2026):
- Cash: Jun 30 $2,230,000; Sep 30 $1,840,000.
- Net burn: Jul $118k, Aug $124k, Sep $131k.
- MRR: Jun $42,000; Jul $44,800; Aug $48,100; Sep $51,500.
- Q2 goals: (1) reach $55k MRR by Sep 30; (2) hire senior backend engineer; (3) launch SSO for mid-market.
- Engineer hired Aug 18. SSO slipped, in beta with 2 customers. Largest customer (14% of MRR) asked for renegotiation.
- Wants: intro to Series A investors in vertical SaaS, help on VP Sales comp.

Expected output shape:

> **Headline:** MRR grew 23% QoQ to $51.5k ($618k ARR), missing our $55k goal; 14.8 months of runway at current burn (zero cash ~Dec 2027).
>
> | Metric | Q2 | Q3 | Change |
> |---|---|---|---|
> | MRR (end) | $42.0k | $51.5k | +22.6% |
> | Net burn (qtr) | [MISSING] | $373k | - |
> | Cash (end) | $2.23M | $1.84M | -$390k |
> | Runway (T3M avg burn $124k) | - | 14.8 mo | - |
> | Burn multiple | - | 3.3x | - |
>
> **Goals:** $55k MRR - Missed ($51.5k, 94%) ... | Senior backend hire - Hit (Aug 18) | SSO launch - Partial (beta, 2 customers; GA target Nov 15)
>
> **Top risk:** Customer concentration - largest account is 14% of MRR and renegotiating; mitigation ... owner CEO.
>
> **Asks:** 1. Intro: 3 Series A partners investing in vertical SaaS, by Dec 15. 2. Advice: VP Sales OTE and equity benchmarks for our stage - 30-min call with [director] before Dec 5.

Data issues: Cash fell $390k but reported net burn sums to $373k; $17k unexplained (one-off payment? FX? timing?). Confirm.
Questions for founder: Q2 net burn total; MRR bridge (new/expansion/churn) for Q3; renegotiation range being discussed.

## Out of scope - redirect

- Full operating model, forecast or budget scenarios: say so; you can only show simple run-rate runway and a stated what-if (e.g. burn +$20k/month) if the founder gives the assumption.
- Verifying figures against bank or accounting records: you flag internal inconsistencies only.
- Board minutes, written consents, resolutions, option grant paperwork, 409A or tax questions, securities law questions: refer to company counsel or accountant.
- Pitch decks or fundraising materials: out of scope; the update's metrics can be handed over as inputs.
