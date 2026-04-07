# Design System — Suriname Cruise Services Catalogue

## Product Context
- **What this is:** Official B2B directory of cruise service providers for Paramaribo, Suriname. Published by SITA (Suriname Investment & Trade Agency).
- **Who it's for:** Cruise line procurement managers, port agents, shore excursion planners — international professionals sourcing local Surinamese suppliers.
- **Space/industry:** Cruise industry trade catalogue. Peers: island port directories, maritime trade catalogues, tourism trade publications.
- **Project type:** Static web app (GitHub Pages), single-page catalogue with JavaScript-driven navigation.

## Aesthetic Direction
- **Direction:** Luxury / Editorial
- **Decoration level:** Intentional — diagonal pattern texture in the masthead, gold rule accents, subtle warmth throughout
- **Mood:** Premium maritime trade publication. Professional credibility first, warmth second. Feels like a well-designed printed catalogue brought to the web.
- **Reference sites:** sita.sr (client site), dummy prototype `Context/suriname_cruise_catalogue_v2 (2).html`

## Typography
- **Display / Hero:** Playfair Display (serif, italic variant) — editorial credibility, premium maritime feel expected by cruise procurement audience
- **Body:** DM Sans — readable, professional, slightly warmer than Inter
- **UI / Labels:** DM Sans (same as body, 500 weight for labels)
- **Data / Tables:** DM Sans with tabular figures
- **Code:** N/A
- **Loading:** Google Fonts CDN — `Playfair+Display:ital,wght@0,400;0,600;1,400` + `DM+Sans:opsz,wght@9..40,300;9..40,400;9..40,500`
- **Scale:** 10px (eyebrow caps) / 11px (meta) / 12px (small) / 13px (body-sm) / 14px (body) / 16px (card heading) / 17px (list item) / 20px (section) / 26px (list title) / 28px (detail heading) / 42px (masthead hero)

## Color
- **Approach:** Restrained — one strong accent (gold) on a navy/cream base; color used for category differentiation in the category grid
- **Primary:** `#1A3A5C` (Deep Navy) — authority, maritime tradition, SITA brand
- **Accent:** `#E8A020` (Gold) — premium quality signal, contrast on navy, used sparingly for rules and highlights
- **Ocean:** `#2E6DA4` — interactive elements (links, hover states)
- **Sky:** `#D6E8F5` — Marine category background, form fields
- **Background:** `#F7F4EE` (Warm Sand) — warmer than white, reduces eye strain, premium tactile quality
- **Surface:** `#FDFCF9` (Cream) — card backgrounds
- **Text:** `#1A1A1A` (Ink), `#6B6860` (Muted)
- **Border:** `#E8E4DA`
- **Category colors:** Teal (#1D9E75), Coral (#D85A30), Plum (#534AB7), Rose (#D4537E), Sage (#3B6D11), Slate (#5F5E5A) — each category has its own identity color
- **Dark mode:** Not implemented (out of scope for this phase)

## Spacing
- **Base unit:** 8px
- **Density:** Comfortable — generous padding on cards (28px), tight enough to feel professional
- **Scale:** 4 / 8 / 12 / 16 / 20 / 24 / 28 / 32 / 40 / 48 / 60

## Layout
- **Approach:** Grid-disciplined — procurement users need to scan and find quickly
- **Home grid:** 4 columns (desktop), 2 columns (tablet), 1 column (mobile)
- **Detail layout:** 2-column (sidebar contact + main content), collapses to 1 column on mobile
- **Max content width:** 1100px
- **Border radius:** Cards 12px / large cards 16px / tags 4-5px / buttons 6-8px / icon wraps 10px

## Motion
- **Approach:** Minimal-functional — only hover state transitions
- **Duration:** 120–150ms for hover state changes (border color, transform)
- **Easing:** CSS default (ease) for hover transitions

## Decisions Log
| Date | Decision | Rationale |
|------|----------|-----------|
| 2026-04-07 | Used dummy prototype color system (navy/gold/cream) | Already appropriate for B2B maritime audience; no reason to diverge |
| 2026-04-07 | Kept Playfair Display + DM Sans | Established pair from dummy; editorial credibility fits procurement audience |
| 2026-04-07 | Warm Sand (#F7F4EE) background | Premium tactile quality vs. clinical white common in B2B directories |
| 2026-04-07 | Show all 8 categories, empty ones muted with CTA | Honest about early-stage directory; sets growth expectation; drives registrations |
| 2026-04-07 | Excluded Papi and kripa.nl (test/fake data) | User decision — only real verified companies in live catalogue |
| 2026-04-07 | Single HTML file, no framework | GitHub Pages static hosting, zero build step, fast load, easy maintenance |
