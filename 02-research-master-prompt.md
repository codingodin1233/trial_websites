# Master Research Prompt (paste into ChatGPT, Gemini, or Claude)

Fill in the three brackets, paste everything under the line, and send.
The sections are ordered by importance. Part 1 carries about 80% of what a good small-business website needs. If you run out of time or sources, finish Part 1 first and stop there.

Fill in:
- BUSINESS: [business name]
- LOCATION: [city, state/country]
- STARTING LINKS: [Google Maps listing, website, Facebook/Instagram, delivery or review pages, if any]

---

## ROLE

You are a research analyst preparing a brief for a web designer who will build a one-page website for a local business. The designer cannot visit the business or call the owner. Everything you return must be checkable.

## RULES (these apply to every line you write)

1. Every fact ends with `[source URL, date checked]`. If you cannot find it, write `UNKNOWN`. Never guess, round, or "fill in what is typical."
2. Prefer first-party sources (their website, Google Business Profile, official social page, official menu). Use reviews and directories only to confirm or to learn customer language.
3. If two sources disagree, list BOTH with links and mark `CONFLICT`. Do not pick one.
4. Label every item: `VERIFIED` (first-party or two agreeing sources), `SINGLE-SOURCE`, or `UNKNOWN`.
5. Do not use marketing words the business has not used about itself ("best", "authentic", "famous", "#1"). Report what they say, in quotes under 15 words, with a link.
6. Do not describe a photo as showing the business unless it comes from the business's own pages.
7. Ignore anything older than 12 months for hours, prices, and staff unless nothing newer exists. Say so when you do.
8. Do not write copy, headlines, or design yet. Research only. Part 5 is the only place for suggestions, and they must be labeled as suggestions.

---

## PART 1. THE 80% (do this first, and do it carefully)

### 1.1 The one action
What do customers actually do to buy from this business: call, walk in, book, text, order online, request a quote? Which one is the main one, and what is the evidence (review mentions, listing buttons, their own site)?

### 1.2 Facts the site cannot get wrong
- Exact business name as it appears on the listing and signage
- Full address and a maps link
- Phone number (and whether it is call-only, text-friendly, or both)
- Email, if published
- Opening hours for EVERY day, including holidays or "by appointment"
- Time zone
- Any "temporarily closed", "moved", or seasonal notes

### 1.3 What they sell, and what it costs
- Full menu or service list, grouped the way the business groups it
- Prices, exactly as published, with the date and where
- If prices are not published, write `PRICE NOT PUBLISHED`
- Anything popular or signature that reviewers mention by name

### 1.4 What customers say (the "shortcut" section)
Read at least 25 recent reviews across Google plus one other platform. Return:
- The 5 words or phrases customers repeat most when praising the business (use their words, not yours)
- The top 3 complaints or doubts
- The top 3 questions customers ask before visiting or ordering (parking, wait time, payment, dietary needs, groups, hours)
- One-line summary: why do people choose this place over the one next door?

### 1.5 The problem the website must solve
In two or three sentences: who is the typical visitor, what are they trying to do right now, and what stops them? (Example: "Someone nearby at night wants to know if the stand is still open and how to get there.")

### 1.6 Photos the business owns
List links to photos on the business's own pages (website, Facebook, Instagram, Google listing). For each: what it shows, and whether it looks usable (sharp, well lit, no people's faces without context). Do not download or re-host anything. Just link.

---

## PART 2. TRUST AND PROOF

- Rating and review count, with platform and date
- Up to 3 short customer quotes (under 15 words each) with link and platform. Do not combine or edit them.
- Years in business, ownership, or story facts, ONLY if published by the business or a credible article
- Certifications, licenses, awards, memberships, with proof links
- Press mentions, with links
- Anything that would be risky to claim (alleged "family-owned", "award-winning", "since 19XX") and why

---

## PART 3. LOCAL CONTEXT

- 3 nearby competitors in the same category. For each: name, link, their main promise in their own words, how they handle the main action (call/book/order), and one thing their site does well and one thing it does badly
- What customers in this area search for: 5 realistic search phrases (for example "breakfast tacos near [neighborhood]"), with a note on where you found the idea
- Neighborhood or landmark names customers use to describe the location
- Parking, transit, or access details people mention

---

## PART 4. LOOK AND FEEL EVIDENCE

- The business's own colors, logo, fonts, signage style, from their own pages (describe in words and give hex values only if you can read them from the logo file or brand page)
- What visual conventions are normal for this industry in this region (for example, taquerias lean warm and bold, dentists lean calm and light)
- 3 reference websites worth borrowing patterns from, from any industry. For each: link, and ONE specific thing to borrow (hero style, menu layout, hours display, mobile call bar). Do not suggest copying designs.

---

## PART 5. FREE PHOTO SHORTLIST (for demos only)

For each slot below, give 2 candidates from Unsplash (unsplash.com) only:
Slots: hero (signature item), close-up of main product, breakfast or secondary product, drinks, a "place" shot (counter, patio, storefront, truck).
For each candidate return: the Unsplash photo PAGE link, the photographer, and the license line. Only list photos whose page says "Free to use under the Unsplash License" (not "Unsplash+"). Say what the photo actually shows, from its title or tags, and whether it clearly matches the slot. If you cannot open the page, write `COULD NOT VERIFY` and do not include it.

---

## PART 6. OUTPUT FORMAT

Return one document in this order:

1. **Top 10 facts** (the ten most important lines from Part 1, one line each, with source)
2. **Conflicts and unknowns** (a table: item, what each source says, what I need from the owner)
3. **Part 1 through Part 5**, using the numbering above
4. **Questions for the owner** (maximum 8, plain language, only things that research could not settle)
5. **Source list** with URL, date checked, and what each source was used for
6. **Honesty note**: list which sources you could not open, and which sections have thin evidence

Do not include design opinions or marketing copy. Do not repeat the same fact in several sections. Keep the whole brief under 3,000 words unless the business is large.

---

## FOR THE DESIGNER (Claude): what to do with the result

1. Run it through `00-build-gate.md`. Anything `UNKNOWN`, `SINGLE-SOURCE`, or `CONFLICT` becomes Assumed and cannot appear as fact.
2. Build the short plan from `01-build-playbook.md` section 3 using the "Top 10 facts" and Part 1.4 customer words for headlines.
3. Use the customers' repeated phrases as headline and section wording where the business also makes that claim. This is the cheapest way to sound right.
4. Photos: demo builds use the Part 5 shortlist after re-checking each page. Client builds use only photos the owner supplies.
