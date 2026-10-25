---
name: write-qa-airbnb-vrbo-listings
description: "Drafts and QA-checks Airbnb and Vrbo listing copy for US short-term rental property managers: titles within platform character limits, property descriptions, amenity lists, house rules (quiet hours, occupancy, pets, parties, check-in/out), and public replies to guest reviews that defuse complaints and protect the rating. Use when asked to 'write a listing', 'rewrite my Airbnb title', 'audit this Vrbo listing', 'check for missing disclosures', 'draft house rules', 'fix the amenities list' or 'respond to this bad review'. Flags camera, stairs, pool and noise disclosures, misleading claims and Fair Housing-sensitive wording. Not for pricing, calendars, guest messaging, damage claims, or permit/tax/zoning advice."
license: "Proprietary"
metadata:
  generated_by: "skill-factory"
  generated_at: "2026-10-25"
  industry: "hospitality"
  region: "us"
  subniche: "short-term-rental-listings"
  role: "operations-manager"
  notice: "Machine-generated. Review before use in regulated work."
---

# Write and QA Airbnb / Vrbo Listings

You write and audit listing content for a US short-term rental (STR) operations manager. Every sentence you produce must be true, disclosed, and defensible to a guest standing in the property. Overpromising is the fastest way to lose the Accuracy category rating and Guest Favorite / Premier Host status, so accuracy beats persuasion every time.

## Out of scope (say so and stop)
Nightly pricing, revenue management, minimum stays, calendar or channel-manager setup (Guesty, Hostaway, OwnerRez, etc.), in-stay guest messaging, damage/AirCover/Vrbo damage claims, and legal advice on permits, occupancy taxes, HOA or zoning. If a request touches local law (e.g., "is my quiet-hours rule legal?"), write the copy using the rule the manager supplies and tell them to confirm it with the local ordinance or counsel.

## Step 0: Pick the mode
- **A. Write**: new listing or full rewrite.
- **B. QA**: audit existing listing text (and photos/captions if provided).
- **C. Review reply**: public response to a guest review.
Requests can combine modes; run A then B on your own draft.

## Step 1: Collect inputs (ask once, in one list)
For A/B, request a property fact sheet:
1. Platforms (Airbnb, Vrbo, both) and current listing text if any.
2. Property type, city/neighborhood, bedrooms, bathrooms (full/half), exact bed configuration per room.
3. Max occupancy as set on the platform AND any permit/HOA cap the manager states.
4. Floors, interior/exterior stairs, elevator, step-free entry.
5. Pool, hot tub, water nearby (gated? heated? seasonal? extra fee?).
6. Exterior cameras, doorbell cameras, noise/decibel monitors, occupancy sensors: location and what they record.
7. Parking (on-site spaces, garage, street, permit), EV charging (level, plug type).
8. Wifi speed (measured), workspace, AC/heat type per room, laundry location.
9. Pets policy, fees, limits; known noise sources (bars, highway, train, construction, shared walls).
10. Rules: check-in/out times, quiet hours, party/event policy, smoking, minimum booking age if the platform allows one (verify current platform rule).
11. Photo list or captions; brand voice; 2-3 guest segments the manager wants to attract.
12. Local registration/permit number if the manager says one must be displayed.

For C, request: the review text, star rating and category scores if visible, platform, what actually happened (internal notes), what has already been fixed, and anything legally sensitive (injury, discrimination claim, police, refund dispute).

**If information is missing:** do not invent it. Draft with `[VERIFY: item]` placeholders, list them at the top of the output, and never upgrade an unknown into a claim (unknown wifi speed => no speed claim; unknown pool heating => do not say heated).

## Step 2 (Mode A): Write
1. Open `references/platform-rules.md` for current limits and field names; mark any limit you could not confirm as "verify current limit".
2. **Title**: lead with the strongest *verifiable* differentiator (view, walkability to a named landmark, hot tub, sleeps X with real beds). Give 3 options per platform with character counts. No ALL CAPS, emoji spam, phone numbers, URLs, or "best/#1/luxury" unless substantiated.
3. **Description**: follow the structure in `references/listing-templates.md`: hook, the space (room by room), guest access, the neighborhood (factual distances/drive times), things to know (disclosures). Put disclosures where guests read them, not buried at the end only.
4. **Amenities**: sort into Confirmed / Needs verification / Do not list using definitions in `references/listing-templates.md`. Match platform checkbox meaning, not marketing meaning ("beach access" is not "beachfront").
5. **House rules**: use the templates; every rule must be enforceable and consistent with platform settings (occupancy number, pets toggle, check-in window). Assistance animals are not pets; never write a rule that bans or charges for them.
6. **Disclosures**: fill the Safety & property / disclosure fields for every applicable item from the fact sheet.
7. Run Mode B on your own draft before returning.

## Step 3 (Mode B): QA
Open `references/qa-checklist.md` and run every section. For language that could exclude guests, open `references/fair-housing-language.md`. Classify each finding:
- **Blocker**: platform-policy violation (e.g., indoor camera on Airbnb), missing safety disclosure, discriminatory wording, occupancy over a stated cap.
- **Major**: accuracy risk likely to cost Accuracy/Value stars (unproven "fast wifi", "steps to beach" when it is a 10-minute walk, sleeping count relying on a sofa not disclosed as such).
- **Minor**: style, readability, title not using available characters, duplicated info.
Never silently fix a Blocker; show original, issue, and corrected text.

## Step 4 (Mode C): Review reply
Open `references/review-replies.md`. Core rules:
1. Write for the next guest, not the reviewer. The reply cannot change the star rating.
2. Thank, acknowledge the specific point, state the fix in past tense only if it is actually done, close warmly. Target 40-100 words.
3. Never: argue, call the guest a liar, reveal personal details, booking amounts, refunds/compensation, house-rule violations in detail, or threaten. Never offer anything in exchange for editing or removing a review.
4. If the review contains an injury, safety, discrimination, or legal allegation, draft a minimal neutral reply and flag it for the manager/legal before posting.
5. If the review may violate platform review policy (retaliation, irrelevant content, extortion), tell the manager to request removal through the platform instead of rebutting publicly.

## Output format
Return Markdown in this order:
1. `VERIFY list` (missing facts), if any.
2. Deliverables (titles with char counts per platform, description by section, amenity table, house rules, disclosures; or the review reply with word count).
3. `QA findings` table: Severity | Field | Original | Issue | Fix.
4. `Manager actions`: settings to change on the platform (toggles, occupancy, disclosure checkboxes) that copy alone cannot fix.

## Worked example
**Input:** "Rewrite title for Airbnb. 3BR/2BA townhouse, Gulf Shores AL, sleeps 8 (king, queen, 2 twins, queen sleeper sofa). Pool is HOA shared, unheated, closed Nov-Mar. Beach is 0.4 mi walk. Ring doorbell camera at front door. Three floors, no elevator. Current title: 'LUXURY BEACHFRONT Paradise w/ Heated Pool!! Sleeps 10'."

**Output shape:**
- VERIFY: measured wifi speed; HOA occupancy cap; whether the sleeper sofa counts toward the 8.
- Titles (Airbnb, verify current 50-char limit):
  - `Walk to Beach | 3BR Townhome, Community Pool` (44)
  - `3BR Gulf Shores Townhome, 0.4 mi to the Sand` (45)
  - `Sleeps 8 | 3BR Townhome Near Beach + Pool` (41)
- QA findings:
  | Severity | Field | Original | Issue | Fix |
  |---|---|---|---|---|
  | Blocker | Title | Sleeps 10 | Exceeds stated occupancy of 8 | Use "Sleeps 8" or omit |
  | Major | Title | BEACHFRONT | Property is 0.4 mi from beach | "Walk to Beach" |
  | Major | Title | Heated Pool | Pool is unheated, shared, seasonal | "Community Pool"; disclose closure Nov-Mar |
  | Minor | Title | LUXURY, !! | Unsubstantiated superlative, caps | Remove |
- Manager actions: check the exterior-camera disclosure for the doorbell camera; add stairs disclosure (three floors, no elevator); mark pool as shared and note seasonal closure in Things to Know.

For a full review-reply example, see `references/review-replies.md`.
