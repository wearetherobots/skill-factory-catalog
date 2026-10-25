# Identity verification for DSARs

Open this at Step 2. Legal anchors: Art. 12(2) (facilitate the exercise of rights), Art. 12(6) (where reasonable doubts exist, you may request additional information necessary to confirm identity), Art. 11(2) (if you cannot identify the person, inform them where possible), Art. 5(1)(c) data minimisation. Detailed guidance: EDPB Guidelines 01/2022 on the right of access — verify the current version.

## Principles

- Verification must be proportionate to the risk of disclosing data to the wrong person, and to the sensitivity of what you hold.
- Use what you already have (authenticated session, registered email, 2FA) before asking for anything new.
- Do not ask for an ID document by default. If you must, ask for the minimum and tell the person to redact everything except name, photo and expiry (and not to send ID numbers unless needed). Delete the copy once verified; log only "verified on <date> by <method>".
- Do not ask for information you do not already hold — you have nothing to match it against.
- Do not make the requester create an account just to make a request.

## Risk tiers

| Tier | Situation | Sufficient verification |
|---|---|---|
| 1 Low | Request from registered account email, in-app while logged in, or support chat on an authenticated session | None beyond the match. Record it. |
| 2 Medium | Request from an unknown email but names an existing account; or data includes payment history, location or detailed activity | Send a confirmation link or code to the registered email/phone, or ask them to submit via the logged-in app. |
| 3 High | Suspected account takeover; special category data; ex-employee or HR data; high-value or contested account; registered email no longer accessible | Combination: control of registered channel plus knowledge check from data you hold (e.g. last invoice amount, workspace name), or redacted ID as last resort. Escalate to DPO. |
| None | You hold no data linkable to the identifiers given | Answer that you do not process their data (or cannot identify them, Art. 11(2)), and invite additional identifiers if they believe otherwise. |

## Representatives and third parties

- Lawyer, family member, or other agent: require written authority signed by the data subject (or a power of attorney), plus verification of the data subject at the relevant tier where risk warrants. Verify current national rules on representation.
- Parents/guardians of a child: confirm parental responsibility and consider the child's own interests; escalate.
- DSAR-automation platforms and "privacy rights" services sending requests on behalf of users: check the mandate is genuine and specific to the person; you may verify the data subject directly via the registered channel.
- B2B customer admin asking for data about a member of their workspace: this is not an Art. 15 request from the data subject. It is the controller (customer) instructing you as processor; handle under the DPA.

## Red flags

- Request asks for delivery to a different email than the registered one.
- Recent password reset, new device, or change of account email shortly before the request.
- Requester pressures for speed or for specific fields only (e.g. IP addresses, address history).
In any of these, move one tier up.

## Wording for an ID request (adapt)

> To protect your data, we need to confirm that this request comes from the account holder. Please [click the confirmation link we have sent to the email address registered on your account / submit the request from within the app while logged in]. We will delete any verification information once your identity is confirmed. We received your request on [date] and will respond by [date].
