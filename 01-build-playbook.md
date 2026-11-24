# Build Playbook (master file)

Read this FIRST, before `00-build-gate.md`. If any project file contradicts this one, this one wins.
Written after the Tacos Las Amazonas rebuild, which is the quality bar for every demo.

## 0. Which file does what

| File | Role | Use it for |
|---|---|---|
| `01-build-playbook.md` | Master. Order of work, defaults, what to skip | Every site |
| `00-build-gate.md` | Intake and approval gate | Every site |
| `coding-standards.md` | Code rules | Every site (simple HTML is the default for small sites) |
| `ux-checklist.md` | Design and conversion rules | Every site |
| `WEBSITE_PROJECT_WORKFLOW_FOR_CLAUDE.md` | Full 10-stage process | ONLY large builds: e-commerce, web apps, multi-page sites with 10+ pages. NOT 30-minute builds |

The workflow file asks for a 15-section planning package. That cannot fit in 30 minutes. For small sites, the gate plus the short plan in section 3 below replaces it. Keep its two best rules: never invent facts, and no code before approval.

## 1. Roles of each tool (do not mix these up)

- **Gemini = research only.** It must return the template in section 2, with a source URL and date for every fact.
- **Cline / free models = never the first builder.** Use them for tiny edits at most. Claude builds; if Claude is rate-limited, wait or do research and intake in the meantime.
- **ChatGPT = opinions on look only.** Its review is not QA. It cannot confirm hours, prices, or that buttons work.
- **Claude = intake check, plan, build, QA.**

## 2. Research template (paste this into Gemini)

Give Gemini this and require every line to end with `[source URL, date checked]` or `UNKNOWN`:

1. Business name, category, address, phone, email
2. Opening hours per day (from Google Business Profile or their official page)
3. Full menu or service list with prices (official page, or "price not published")
4. Rating and review count, with platform and date
5. Real claims the business makes about itself (quote and link)
6. Owner or story facts, only if published
7. Photos they actually own (links to their own pages)
8. Social links
9. Three top customer questions seen in reviews
10. Two or three competitors nearby, one line each

Rule: anything marked UNKNOWN or without a source becomes **Assumed** and cannot appear on the page as fact (labeled demo is the only exception).
If two sources disagree (the taco site: header said 7 AM daily, code said Sunday 8 AM), list both and ask. Do not pick one silently.

## 3. Short plan (replaces the full workflow for small sites)

Show this, wait for "approved", then build. One message.

- Verified / Assumed table
- Sitemap and section order
- Primary CTA (one), secondary CTA
- Palette (4 to 6 hex values with names), 2 fonts
- 3 sample headlines (no unverified claims)
- Reference sites: what is taken from each, in one line

## 4. Build defaults for a small business site

1. Stack: ONE self-contained HTML file, vanilla CSS/JS. Move to Next.js only if the site is multi-page and the client needs editing.
2. Mobile first. Fixed Call / Map / Menu bar on phones. Sticky header with one call button.
3. Hero: a plain, specific headline (what + when/where), one primary button, address visible.
4. Open/closed badge computed from real hours in the business time zone, handling after-midnight hours.
5. Menu or services in tabs or a clear list. Prices only if verified or labeled.
6. One memorable thing per site (the hero type or one photo), everything else quiet.
7. Motion: gentle fade-in only, switched off for `prefers-reduced-motion`.
8. Forms must really work. No backend means the form opens a prefilled SMS or mailto and says nothing is sent until the user sends it.
9. Icons are inline SVG. No emoji as icons.
10. Accessibility floor: skip link, visible focus, 48px tap targets, contrast, labels, `rel="noopener"`.
11. Demo builds: visible demo notice, `noindex`, footer credit for photos.

## 5. Photo protocol (the thing that went wrong before)

**Never type an Unsplash photo ID from memory.** The Yori file did this: repeated IDs, one malformed ID, and none checked against what they show. The first taco build inherited them, and the hero was a generic night food truck.

For each photo slot (hero, food close-up, breakfast or product, drinks, detail, place):

1. Search for the specific subject ("unsplash tacos al pastor").
2. Open the Unsplash photo page. Confirm it says "Free to use under the Unsplash License". Skip anything labeled Unsplash+.
3. Take the `https://images.unsplash.com/photo-...` URL from that page. Do not build one by guessing.
4. Check tags and title match the slot. Write the photographer in the footer credit.
5. Add `width`, `height`, `alt`, and `onerror="this.style.display='none'"`. Lazy-load everything except the hero.
6. If no verified photo exists for a slot, use a color panel. A wrong photo is worse than no photo.

**For demos:** stock photos are fine and wanted. Label them "Placeholder photo".
**For paying clients:** stock photos must be replaced with the client's real photos before launch. Never let a stock photo imply it shows their food, truck, or shop.

Preview note: external images can fail to load inside the chat preview. Open the downloaded file in a normal browser before judging the photos.

## 6. QA before handoff (10 minutes, in this order)

1. Parse check: JS has no syntax errors, HTML tags balance.
2. Open the file in a real browser at 375, 768, and 1440 px. No sideways scroll, no clipped text.
3. Tap every button: call, directions, menu tabs, form, mobile bar.
4. Hours badge: change the device time and confirm it flips correctly near midnight.
5. Contrast and keyboard: Tab through the page; focus must be visible.
6. Facts: every hour, price, phone, address matches the verified list. Anything assumed is listed in the handoff note.
7. Score quickly against `ux-checklist.md` (85 or higher, no critical failure).

Claude cannot see the rendered page in chat. Step 2 needs Jam's eyes or screenshots. Send screenshots back so fixes are based on what is on screen.

## 7. Prioritize, do not prioritize, skip

**Prioritize (in this order):** verified intake, one clear CTA, hero headline, mobile action bar, readable menu/services, correct hours and contact, working form, one strong visual idea, real or verified photos.
**Do not prioritize:** more than one font pairing, more than 6 to 8 sections, parallax or fancy animation, schema and analytics on demos, perfect Lighthouse scores on demos, building extra pages.
**Skip for small sites:** personas, 3 to 5 competitor reports, moodboards, multiple design concepts, user testing, Figma, a separate high-fidelity design stage, React.

## 8. Failure log (add a line every time something goes wrong)

| Date | What failed | Cause | Rule added |
|---|---|---|---|
| 2026-11-24 | Cline taco site: unclosed div, mobile bar hidden at all widths, badge logic wrong | Free model built first, no QA | Claude builds; QA step 1 and 3 |
| 2026-11-24 | Stock photos described as the business (patio, "glowing food truck") | No photo protocol | Section 5 |
| 2026-11-24 | Hours contradicted between header and code | Gemini data not cross-checked | Section 2: list conflicts, ask |
| 2026-11-24 | Photos "missing" in preview | Preview blocked external images | Open in a real browser |
