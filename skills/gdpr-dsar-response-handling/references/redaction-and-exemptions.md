# Redaction and withholding

Open this at Step 5. Starting point: the requester gets their personal data. Redaction is narrow and item-by-item; withholding requires a documented ground. Escalate whole-category withholding to the DPO.

## What counts as their personal data

- Any information relating to them, including opinions and assessments (CJEU C-434/16 Nowak: comments on an exam script are personal data of the candidate). Internal notes like "difficult customer, likely to churn" must be disclosed.
- Pseudonymised data (e.g. events keyed by user ID) is personal data. Truly anonymous or aggregated statistics are not.
- Log of who consulted their data: the consultation information may be in scope; the identity of staff who acted under the company's authority is in principle not required unless essential for the person to exercise their rights (CJEU C-579/21). Verify scope with DPO.

## Grounds for redaction or withholding

| Ground | Basis | How to apply |
|---|---|---|
| Rights and freedoms of others | Art. 15(4), Recital 63 | Redact third parties' personal data (other users, colleagues, other customers) where disclosure would harm them. Balance: data already known to the requester (their own email thread), customer-facing staff names, and data the third party consented to share usually stay. |
| Trade secrets / IP | Recital 63 | Withhold specific proprietary content (e.g. detailed scoring model weights, internal pricing algorithms). Still give the personal data and meaningful information. Recital 63: the result must not be a refusal to provide all information. |
| Automated decision logic | Art. 15(1)(h) vs trade secrets | Give meaningful information about the logic, significance and envisaged consequences. Where trade secrets are claimed, verify current CJEU case law (e.g. C-203/22 Dun & Bradstreet Austria) and escalate. |
| Security and fraud | National restriction under Art. 23 or Art. 15(4) | Disclose that a flag or decision exists and the data used; withhold only the detection rules or thresholds whose disclosure would enable circumvention. Verify national law and escalate. |
| Legal privilege | Not in GDPR text; national law via Art. 23 | Communications with lawyers for legal advice or litigation may be exempt under member-state law. Verify with counsel in the relevant member state; never self-certify privilege. |
| Other national restrictions | Art. 23 national implementing laws (e.g. Germany's BDSG) | Only apply a national exemption you have verified for the relevant jurisdiction. Record the provision checked by counsel. |
| Manifestly unfounded/excessive | Art. 12(5) | Applies to the request, not to documents. See deadline-rules.md. |

## Not valid reasons to redact

- Embarrassing, critical or informal comments about the requester.
- "The data is in a format that's hard to export."
- The requester's motive (dispute, complaint, negotiation).
- "They already have it" as a blanket reason: you may summarise data they demonstrably hold, but say so.

## Third-party data: decision steps

1. Is the third party identifiable from the item? If not, no redaction.
2. Is the information already known to the requester (they wrote it, received it, or were present)? Usually disclose.
3. Would disclosure reasonably harm the third party (private info, complaint about the requester, personal contact details)? Redact the identifying parts, keep the content about the requester.
4. Can you get the third party's consent quickly? Optional; refusal does not decide the balance alone.
5. Record the decision in the redaction log.

SaaS examples:
- Comment by another workspace member about the requester: if in a B2B customer workspace, that is processor data (forward). If in a controller context (e.g. community forum), disclose content, consider redacting the author.
- Internal Slack thread about the requester's ticket: disclose the parts about them; redact colleagues' unrelated chatter and, where not essential, their names.
- Support agent names on tickets: customer-facing; normally keep.

## Redaction technique

- Redact in the source export or with a proper redaction tool that removes underlying text; drawing black boxes in a PDF is a known failure.
- Strip document metadata (author, comments, tracked changes).
- Never disclose credentials, password hashes, API keys, session tokens or full card numbers; state that security credentials are held but not reproduced.

## Redaction log (keep in the DSAR file)

| # | Item / location | Redacted or withheld | Ground | Reviewer | Date |
|---|---|---|---|---|---|
| 1 | Slack #support 2026-09-12 | Colleague names redacted | Art. 15(4) | [name] | [date] |
