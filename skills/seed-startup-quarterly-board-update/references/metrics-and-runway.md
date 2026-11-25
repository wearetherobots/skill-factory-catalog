# Metrics, runway and consistency checks

Open this during Steps 2-4. Definitions vary by company; whatever definition the founder uses, state it in the appendix and keep it the same every quarter. If the founder changes a definition, show both the old and new values for the changeover quarter.

## Cash, burn and runway

| Term | Definition | Notes |
|---|---|---|
| Bank cash | Cash and cash equivalents in company accounts at month-end | Exclude signed-but-unfunded SAFEs, undrawn debt, pending grants. List those separately as "committed". |
| Gross burn | Total cash out in the month (payroll, vendors, rent, taxes paid) | Useful for cost-cut scenarios. |
| Net burn | Cash out minus cash in from operations (gross burn - collections) | Exclude equity financing inflows. Show debt draws separately. |
| Runway (months) | Bank cash / average monthly net burn | Default to trailing 3 months. If burn is rising steadily, also show runway at the latest month's burn and say which is lower. |
| Zero-cash date | Month-end of last data point + runway months | Give month and year only. |
| Default alive / dead | Whether the company reaches profitability on current cash at current growth and cost trends | Only state this if the founder supplies a revenue and cost trajectory; otherwise mark it as a question. Do not build the projection. |

One-offs: if a month contains a non-recurring item (annual software prepayment, financing legal fees, R&D tax credit refund, deposit), show net burn both as reported and excluding the one-off, and compute runway on the reported number unless the founder confirms the item will not recur.

Collections timing: annual-upfront billing makes net burn look low in billing months. Note this when net burn swings more than ~30% month to month.

## Revenue-stage B2B SaaS

- MRR: normalized monthly recurring subscription revenue at month-end. Exclude one-time services/implementation fees (report those separately).
- ARR: MRR x 12. Call it run-rate, not contracted ARR, unless contracts support it.
- MRR bridge: opening MRR + new + expansion - contraction - churned = closing MRR.
- Logo churn: customers lost in period / customers at start of period.
- Gross revenue retention (GRR): (opening MRR - contraction - churn) / opening MRR, for the cohort existing at period start. Cannot exceed 100%.
- Net revenue retention (NRR): (opening MRR + expansion - contraction - churn) / opening MRR, same cohort. Usually reported on a trailing 12-month basis; at seed often too few customers to be meaningful - say so if fewer than ~20 customers.
- Burn multiple: net burn in period / net new ARR in period. Lower is better. If net new ARR is zero or negative, report "n/m" (not meaningful), not a number.
- CAC payback (months): sales and marketing spend / (new MRR x gross margin %). Only if gross margin and S&M spend are supplied.
- Concentration: largest customer as % of MRR; top 5 as % of MRR. Flag any single customer above ~10%.
- Pipeline: weighted pipeline by stage, with stage definitions. Do not present unweighted pipeline as a forecast.

## Consumer / prosumer

- DAU, WAU, MAU; DAU/MAU ratio as stickiness.
- Cohort retention (e.g. week 1, week 4, month 3) for monthly signup cohorts. Show the latest three cohorts against the earliest comparable one.
- Activation rate: % of signups completing the defined activation event within N days (state N).
- Paid conversion and ARPU if monetizing.
- Organic vs paid acquisition split; blended and paid CAC.

## Marketplace

- GMV, take rate (net revenue / GMV), net revenue.
- Supply and demand counts, liquidity (e.g. % of listings that transact, time to match).
- Repeat rate of buyers by cohort.
- Contribution margin per transaction if incentives/subsidies are significant.

## Pre-revenue

Use the leading indicators the board agreed on at the last meeting. Typical: signed design partners, pilots live, LOIs (with value), waitlist and activation, technical milestones with dates. Treat LOIs as non-binding; never sum them into "revenue".

## Consistency checks

Run all that the data allows. Report each failure as: what, number A, number B, gap, likely explanations to confirm.

1. Cash roll-forward: opening cash - sum(monthly net burn) + financing inflows = closing cash. Flag gaps above ~2% of quarterly burn.
2. MRR bridge balances to closing MRR.
3. MoM and QoQ growth math: recompute from raw MRR; flag if the founder's stated percentage differs by more than 0.5 points.
4. Runway stated by founder vs computed: flag if different by more than half a month; show the method each used.
5. Headcount vs payroll: headcount up but payroll flat (or vice versa) needs an explanation (start dates, contractors).
6. Customer count vs MRR: average MRR per customer moving sharply without a pricing change.
7. Goal wording: last quarter's goals match what the founder now reports against.
8. Period alignment: all metrics cover the same months; no mixing of fiscal and calendar quarters.
9. Units and currency: thousands vs units, USD vs local currency, ARR vs MRR mix-ups.
10. Retention sanity: GRR > 100% or NRR < GRR indicates a calculation error.

## Formatting numbers on page one

- Money: $51.5k, $1.84M. Keep exact figures in the appendix table.
- Percentages: one decimal for growth and retention.
- Runway: one decimal, plus zero-cash month.
- Always pair a number with its comparison: vs last quarter, vs goal, or vs plan.
