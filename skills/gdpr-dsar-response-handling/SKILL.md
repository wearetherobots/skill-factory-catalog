---
name: gdpr-dsar-response-handling
description: Runs a GDPR Article 15 data subject access request (DSAR / SAR) end to end for a small EU SaaS company. Covers intake logging, the controller-vs-processor check for B2B customer data, proportionate identity verification, the one-month clock and Art. 12(3) extensions, searching product DB, logs, support, CRM, billing and processors, redaction and withholding (third-party data, trade secrets, privileged material), and drafting the response letter with all Art. 15(1)-(2) information. Use when someone says "we got a subject access request", "a user wants all the data we hold on them", "DSAR deadline", "can we extend the SAR", "what do we redact", "verify the requester's ID", or "draft the access request response". Flags bundled erasure, rectification or portability requests but does not process them. Not legal advice; does not cover breaches or regulator complaints.
license: Proprietary
metadata:
  generated_by: skill-factory
  generated_at: "2026-10-25"
  industry: saas
  region: eu
  subniche: gdpr-dsar-handling
  role: compliance-officer
  notice: "Machine-generated. Review before use in regulated work."
---

# GDPR DSAR response handling (Art. 15, small EU SaaS)

You are acting as the compliance officer's working assistant. Produce a defensible, documented response to one access request. You do not replace the DPO or external counsel; escalate where this file says so.

## Scope guard (check first)

- In scope: the right of access under GDPR Art. 15, with the procedural rules in Art. 12.
- Bundled requests: if the message also asks for erasure (Art. 17), rectification (Art. 16), restriction (Art. 18), portability (Art. 20) or objection (Art. 21, incl. marketing opt-out), log each as a separate ticket with its own one-month clock and hand it off. Tell the user you have flagged it. Act on a marketing opt-out immediately anyway; it costs nothing and is low risk.
- Out of scope: breach notification, responding to a supervisory authority complaint or inquiry, litigation disclosure. Stop and route to DPO/counsel.

## Inputs to collect

Ask for whatever is missing; mark unknowns `[CONFIRM: ...]` rather than guessing.

1. The request verbatim, channel (email, in-app, chat, letter, social), and exact date received by anyone in the company.
2. Requester: name, emails, account/user IDs, relationship (end user, customer admin, invited member of a customer's workspace, lead, ex-employee, candidate), and whether a representative is acting.
3. Company role for the data concerned: controller, or processor on behalf of a B2B customer (check the DPA / terms).
4. Record of processing activities (RoPA), system inventory, processor/sub-processor list, retention schedule.
5. DPO contact (if appointed) and the lead / competent supervisory authority.

## Workflow

### Step 1 - Intake and log (day 0)

- Treat it as a DSAR if a person asks for their data or what you do with it, in any wording, any channel, sent to any employee. No form, no GDPR citation and no reason are required.
- Open a DSAR record (fields in the worked example). Date received = the day it reached the company, not the day compliance noticed it.
- Controller/processor split:
  - Data the SaaS decides about (account, billing, marketing, product analytics, support tickets, security logs): you are controller. Continue.
  - Content inside a B2B customer's workspace processed on the customer's instructions: you are processor. Do not answer substantively. Forward to the customer promptly as your DPA requires (Art. 28(3)(e) assistance), tell the requester which organisation is the controller, and offer to assist that controller.
  - Mixed requests are common: answer the controller part, forward the processor part.
- Send an acknowledgement within a few working days (good practice, not a statutory deadline) stating the date received and when to expect a reply.

### Step 2 - Verify identity, proportionately

Open `references/identity-verification.md`. Default rule: if the request comes from the registered account email or a logged-in session, that is normally enough. Do not demand passport copies by default; only ask for more under Art. 12(6) when there are reasonable doubts. Never ask for more data than you already hold to match against.

### Step 3 - Set and manage the clock

Open `references/deadline-rules.md` for date arithmetic, extension, and manifestly unfounded/excessive requests.

- Deadline: one month from receipt (Art. 12(3)). Record the computed date in the log.
- Extension: up to two further months only where necessary given complexity and number of requests, and you must tell the requester within the first month, with reasons.
- Refusal or fee only for manifestly unfounded or excessive requests (Art. 12(5)); burden of proof is on the company. If you will not act, say so within one month with reasons and the right to complain and seek a judicial remedy (Art. 12(4)).
- Whether the clock pauses while you wait for ID: verify current EDPB Guidelines 01/2022 and your authority's practice. Conservative default: ask for ID immediately and treat the clock as running.

### Step 4 - Find the data

Open `references/data-search-checklist.md`. Search every system with every identifier. Send processor assistance requests on day 1-3 with a response date at least 10 days before your deadline. Do not delete or amend data because a request arrived; the response reflects the data held when the request was received.

### Step 5 - Review, redact, withhold

Open `references/redaction-and-exemptions.md`. Redact narrowly; withholding is the exception and must be logged with a reason. Never refuse the whole request because some items are protected. Internal notes and opinions about the requester are their personal data and are not redactable merely because they are awkward.

### Step 6 - Draft the response

Open `references/response-letter-template.md`. The response has two parts:
1. A copy of the personal data (Art. 15(3)) — faithful and intelligible, extracts or whole documents where context is needed (CJEU C-487/21). First copy is free.
2. The supplementary information in Art. 15(1)(a)-(h) and 15(2): purposes, categories, recipients (named where possible, CJEU C-154/21), retention, rights, complaint right, source, automated decision-making, and transfer safeguards.

Tailor to this person — paste-in privacy-notice text alone is a common failure. Use the electronic form if the request was electronic (Art. 12(3)), plain language (Art. 12(1)).

### Step 7 - Deliver and close

- Deliver securely (expiring link to authenticated portal or encrypted archive with password sent by separate channel). Never attach a full export to an unverified email.
- Record: date sent, what was disclosed, redaction log, withholding reasons, extension notice, approver.
- Keep the DSAR file per your retention schedule (`[CONFIRM: retention period for DSAR records]`) and delete any ID documents collected once verification is done.

## Escalate to DPO / counsel when

- Requester is in a dispute, litigation, employment claim or is a journalist or lawyer; or the request looks like pre-action disclosure.
- You intend to refuse, charge a fee, or withhold a whole category of documents.
- Legal privilege, a national Art. 23 restriction, or law-enforcement/fraud material is involved.
- Special category data (Art. 9), children's data, or the requester claims account takeover.
- The processor/customer refuses to cooperate or you will miss the deadline.

## Output format

For each DSAR, produce these sections in order:

1. **DSAR log entry** (table).
2. **Scope and role decision** (controller/processor, bundled rights flagged).
3. **Deadline** (received, due, extension decision with reason).
4. **Identity decision** (tier, evidence relied on, any request sent).
5. **Search plan** (system, identifiers, owner, due date, status).
6. **Redaction/withholding log** (item, ground, decision).
7. **Draft response letter** and any interim letters.
8. **Open items** listed as `[CONFIRM: ...]`.

If information is missing, still produce all sections with placeholders and list the questions at the top; never invent recipients, retention periods or sub-processors.

## Worked example

**Input:** "Got this in Intercom on 31 Oct 2026 from anna.k@example.com: 'Please send me everything you have on me, and also delete my account after.' She's on our Pro plan, user ID u_48213, and she's also a member of Acme GmbH's workspace."

**Expected output shape:**

| Field | Value |
|---|---|
| DSAR ID | DSAR-2026-014 |
| Received | 2026-10-31 via Intercom |
| Requester | Anna K., anna.k@example.com, u_48213 |
| Rights requested | Access (Art. 15); erasure (Art. 17) logged separately as DSAR-2026-015 |
| Role | Controller for account, billing, analytics, support; processor for content in Acme GmbH workspace |
| Identity | Tier 1: request from logged-in Intercom session matching registered email; no further ID |
| Due | 2026-11-30 (no 31 November, so last day of month; verify weekend/holiday handling) |
| Extension | Not needed |

- Role note: forward the Acme workspace part to Acme GmbH's admin per DPA; tell Anna that Acme is controller for that content.
- Erasure note: hold erasure until the access response is delivered, and tell Anna you are doing so; do not erase data in scope of the pending access request.
- Search plan rows: Postgres users/events (eng, due 11-10), Stripe (finance, 11-10), Intercom + HubSpot (support/sales, 11-10), Mixpanel by distinct_id (product, 11-12), Sentry/app logs 30-day window (eng, 11-12), sub-processor requests sent 11-02 due 11-16.
- Redaction log: support agent first names kept (customer-facing, already known); internal Slack thread naming two colleagues: keep the content about Anna, redact colleague identities unless essential.
- Letter: from the template with all Art. 15(1)(a)-(h) headings filled, export as JSON + CSV + PDF summary via expiring portal link.
