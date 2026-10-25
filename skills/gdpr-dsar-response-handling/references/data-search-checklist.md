# Data search checklist for a SaaS DSAR

Open this at Step 4. Goal: find all personal data relating to the requester for which the company is controller, including data held for you by processors.

## 1. Build the identifier set first

Collect every key that links to the person, then search each system with all of them:
- Email addresses (current, previous, aliases, plus-addresses), name variants
- Internal user ID, account/tenant ID, workspace memberships
- Billing customer ID (e.g. Stripe `cus_...`), invoice numbers, VAT ID for sole traders
- CRM contact/lead IDs, support requester IDs
- Analytics IDs (distinct_id, anonymous IDs merged on login), cookie IDs, device IDs, push tokens
- Phone numbers, IP addresses tied to their sessions (beware shared/NAT IPs: only include data you can link to them)

## 2. Systems to search

Adapt to the company's RoPA; mark each row searched / not applicable / data found.

| Area | Typical systems | What to pull |
|---|---|---|
| Product database | Postgres/MySQL, MongoDB | Profile, settings, memberships, roles, content they created (controller part only), activity/event tables, consent records, deleted-but-retained rows |
| Auth | Auth0, Cognito, Firebase Auth, in-house | Login history, MFA methods (do not disclose secrets or hashes), SSO links |
| Logs | App logs, audit logs, CDN/WAF, load balancer | Records with their user ID or IP within retention window; summarise high-volume logs if a faithful extract keeps them intelligible |
| Error/observability | Sentry, Datadog | Events containing their identifiers |
| Analytics | Mixpanel, Amplitude, GA4, PostHog, Hotjar | User profile, event history, session recordings |
| Data warehouse | BigQuery, Snowflake, Redshift, dbt models | Copies of the above; enrichment tables; scores/segments |
| Billing | Stripe, Chargebee, Paddle, accounting tool | Payment history, invoices, payment method metadata (last 4 digits, not full PAN), dunning notes |
| Support | Zendesk, Intercom, Freshdesk, Help Scout | Tickets, chat transcripts, internal notes, CSAT, call recordings |
| CRM/sales | HubSpot, Salesforce, Pipedrive, call recorders (Gong) | Contact record, notes, call recordings/transcripts, enrichment data and its source |
| Marketing | Mailchimp, Customer.io, Brevo, ad platforms | Lists, campaign engagement, consent/opt-out history, custom audiences uploads |
| Internal comms | Slack/Teams, staff email, Google Drive/Notion, Jira/Linear | Messages and docs about the person (search name and email) |
| Security/fraud | Fraud tools, abuse queues, ban lists | Flags, scores, decisions (see redaction file on security logic) |
| AI features | LLM providers, prompt/response logs, vector stores | Prompts and outputs linked to their account |
| HR (if ex-employee/candidate) | HRIS, ATS (Personio, Greenhouse), payroll | Escalate: HR DSARs usually need counsel review |
| Backups | DB snapshots, archives | In scope in principle; verify current EDPB guidance on effort and practical approach. Document what exists and its expiry if you do not restore |

## 3. Processors

- From the sub-processor list, identify every processor holding their data. Most SaaS tools offer an admin export or a privacy API; use that before writing to the vendor.
- Where you need vendor help, invoke the DPA's data-subject-rights assistance clause (Art. 28(3)(e)) in writing:

> Under clause [x] of our DPA, please provide all personal data you process on our behalf relating to [identifiers] by [date]. Do not contact the data subject. Reference: [DSAR ID].

- If the company is processor for a B2B customer, the direction reverses: you assist the customer; you do not answer the data subject.

## 4. Rules while searching

- Do not delete, amend or anonymise data because a request arrived. Note any routine deletions that occur under the retention schedule and verify the current position on whether to pause them for in-scope records.
- Record who searched what, when, and with which identifiers. Gaps in the search log are the most common finding in complaints.
- Capture recipient names as you go (each tool, vendor, integration, customer workspace admin who received the data): you will need them for Art. 15(1)(c).
- Capture the source of any data not collected from the person (enrichment vendors, referrals, workspace invitations by another user) for Art. 15(1)(g).
