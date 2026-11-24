# Skills: Food Truck / Local Food Business Website

A reusable component library and decision framework extracted from real, good-looking sites (Yori Korean BBQ and 10/10 Lawn & Landscape). This is **not** a rigid template — it's a set of patterns you pick from based on what each business actually needs.

---

## 1. Component Library

These are the building blocks that appear across Yori and 10/10. Copy the ones that fit; skip the ones that don't.

### A. Sticky Header
Both sites use a fixed/sticky top bar so the phone and navigation never leave the screen.

**Yori pattern:** dark translucent background, brand mark + name on left, nav links + CTA button on right, hamburger menu on mobile.

**10/10 pattern:** dark bar, logo + phone CTA button, nav hidden on mobile (shown on desktop), sticky at top with safe-area padding.

### B. Hero Section
Big image + headline + one or two clear actions.

**Yori pattern:** full-bleed photo with dark gradient overlay, eyebrow label, large serif H1, short copy, two buttons (primary + outline).

**10/10 pattern:** illustrated or photo hero with copy on the left, two buttons stacked vertically.

### C. Section Header Rhythm
Every section uses: eyebrow (small, uppercase, colored) → H2 (serif, large) → short intro paragraph → optional action link.

### D. Button System
Three variants: primary (filled), outline (transparent with border), dark/ghost. All have hover lift/brightness, min-height 50px+, uppercase small text.

### E. Photo Grid / Tiles
Yori uses 3-column menu cards with food photos. 10/10 uses 3-column work tiles with illustrated (replaceable with real) photos. Both use `object-fit: cover` and aspect ratios.

### F. Contact / Visit Block
Grid of labeled rows: Address, Phone (tap-to-call), Hours, Social. Yori pairs it with a "visit card" aside containing the same phone + directions.

### G. Floating / Bottom CTA Bar
Yori has a floating call button bottom-right. 10/10 has a full-width bottom callbar on mobile. Both make the phone one thumb-tap away.


## 2. Business-Problem Mapping

Don't apply every component to every business. Match the pattern to the problem the business solves for its customers.

| Business type | Core customer problem | Components to prioritize | Components to skip or minimize |
|---------------|----------------------|--------------------------|-------------------------------|
| **Food truck / late-night eatery** | "Where are you? Are you open? Can I order ahead?" | Sticky header with phone, Open Now badge, hours front-and-center, featured items with photos, SMS/large-order path, Google Maps link | Multi-page sections, long "about" story, reservation widgets |
| **Restaurant / BBQ / dine-in** | "What's the vibe? Can I bring a group? What's on the menu?" | Hero experience photo, intro strip ("Made for sharing"), story section, menu cards, gallery, visit/contact with address + phone | Seasonal picker, bottom callbar (less critical if they take reservations) |
| **Landscaping / home service** | "Do you serve my area? Can I see your work? Call for estimate." | Huge phone number, service area statement, work tiles/photos, services grid with icons, seasonal availability | Food photos, late-night hours badge, SMS ordering |
| **Retail / boutique** | "What do you sell? Is it in stock? Where is the shop?" | Product grid, store hours, address + map, online shop link, contact | Service-area grids, experience sections |

### Problem → Design decision examples

**Food truck: "Are you open right now?"**
→ Large "Open Now / Closed" badge near the top, hours listed inline with address and phone on first screen.

**Food truck: "What should I order?"**
→ Featured items section with 3–4 popular tacos, photo + price + one-line description.

**Restaurant: "Can I bring 8 people?"**
→ Story section about sharing, menu cards that say "ask about group options," visit card with phone + Facebook messenger.

**Landscaping: "Do you work in my neighborhood?"**
→ Service area section with town names, "call and ask" CTA, work tiles showing local yards.


## 3. Content Checklist (gather before designing)

For any local food or service business, get these from the owner:

**Must-have:**
- Business name + tagline
- Address / service area
- Phone number (tap-to-call link)
- Hours of operation (per day)
- Primary customer action (call, order ahead, visit, message on social)

**Nice-to-have:**
- Signature dish or service
- Social proof (review count, rating, customer quote)
- Photos (real if available, Unsplash placeholders if not)
- Social media links
- Catering / large-order contact method

**For food trucks specifically:**
- Is the location fixed or rotating?
- Late-night vs. breakfast hours?
- SMS or phone for large orders?
- Delivery partners (DoorDash, Toast, etc.)?


## 4. Tailoring Guide (how to deviate from the pattern)

### If the business has NO public phone
→ Replace phone CTA with "Message us on Facebook/Instagram" or a contact form. Don't fake a number.

### If the menu changes weekly
→ Don't hardcode prices. Use a "Message for current menu" pattern (like Yori's menu cards linking to social).

### If the business is appointment-only
→ Replace "Order now" with "Book a visit" + calendar link. Remove walk-up language.

### If the brand is luxury / high-end
→ Use more whitespace, serif-only typography, darker palette, fewer photos (quality over quantity). Skip the "thumb-zone callbar."

### If the brand is fast / casual
→ Bold colors, large food photos, prominent prices, SMS ordering, late-night badge.

## 5. Image Sourcing Rules

**Unsplash direct URLs** (same pattern Yori and 10/10 use):
```
https://images.unsplash.com/photo-ID?auto=format&fit=crop&w=1200&q=85
```

- Always add `loading="lazy"` and `alt` text describing the image.
- Use `object-fit: cover` with fixed height containers so layout doesn't shift.
- Real photos beat AI-generated or generic illustrations for appetite and trust.
- When the owner provides real photos, swap the `src` — no other changes needed.

**Photo slots for a food truck:**
1. Hero banner (truck exterior, night or day)
2. Featured items (3–4 top dishes)
3. Salsa bar / condiments
4. Patio / seating area
5. Location / neighborhood context

## 6. Mobile-First UX Rules

- **Thumb zone:** Primary CTAs (call, directions, order) within bottom 40% of screen on mobile.
- **No pop-ups:** They block the menu on phones. Use banners instead.
- **Text menu, not PDF:** Reads on any phone, searchable, updates in minutes.
- **Tap-to-call:** `href="tel:+1..."` on every phone number.
- **One column on mobile:** Stack sections vertically; only go multi-column on desktop (760px+).
- **Touch targets:** Buttons min-height 50px, links spaced so they don't overlap.

---

*Extracted from: yori_business_v1.html, 10_10_business_v1.html, index.html (Business Web Development portfolio)*
