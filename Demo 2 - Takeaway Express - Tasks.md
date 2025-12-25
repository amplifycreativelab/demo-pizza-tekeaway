# Development Tasks - Demo 2 (Takeaway / Pizza)

Source docs:

- `docs/global prompt.md`
- `pizza-takeaway-demo/demo2- prompt.md`

How to use:

- Mark items complete by changing `- [ ]` to `- [x]`.
- Work top-to-bottom; sections later in the file may depend on earlier setup tasks.

## Phase 0 - Project Decisions

- [ ] Confirm GitHub Pages repo name for Astro `base` (must be `"/<repo>/"`).
- [ ] Choose styling approach: Tailwind OR CSS modules + tokens (Tailwind required by the Demo 2 brief).
- [ ] Choose fonts (max 2): condensed/bold headings + legible sans body.
- [ ] Confirm business placeholders (name, phone, address area in Perth WA, hours, cuisine).
- [ ] Confirm ordering flow (phone-first + delivery platform click-through + "Quick Add" behavior).

## Phase 1 - Astro Setup (Static + GitHub Pages)

- [ ] Create a new Astro project (static output).
- [ ] Configure `astro.config.mjs` with `site: "https://github.com/amplifycreativelab"` and `base: "/<repo>/"`.
- [ ] Ensure all internal links and asset URLs work under the base path (no hard-coded absolute `/` paths).
- [ ] Add/verify npm scripts: `dev`, `build`, `preview`.
- [x] Add `src/assets/images/` placeholder images (hero, best sellers, deals, menu items, OG image).

## Phase 2 - Design System (Street-Food Premium)

- [ ] Define color palette: `#D92228` (primary), `#FFFBF2` (background), `#F5A623` (accent), `#1A1A1A` (text/borders).
- [ ] Define spacing scale (4/8/12/16/24/32/48/64).
- [ ] Define typography scale (H1/H2/body/labels) with strong hierarchy (uppercase H1/H2).
- [ ] Implement focus-visible styles for links/buttons/inputs.
- [ ] Implement reduced motion support (`prefers-reduced-motion`).

If using Tailwind:

- [ ] Install/configure Tailwind for Astro.
- [ ] Add Tailwind theme tokens (colors, font families, spacing, radii, shadows).

If using CSS modules + tokens:

- [ ] Create `src/styles/tokens.css` (colors, font families, spacing, radii, shadows).
- [ ] Create base/global styles (typography defaults, container widths, utilities).

## Phase 3 - Core Layout & Shared Components

- [ ] Create `src/layouts/BaseLayout.astro` with:
  - [ ] Skip link
  - [ ] Header/nav (logo left; Menu/Deals links; prominent Order button on desktop)
  - [ ] Sticky mobile bottom bar (Call + Order)
  - [ ] Footer with NAP + hours + pickup instructions + parking
  - [ ] Title/meta slots
  - [ ] OG/Twitter meta placeholders
- [ ] Build design-system components (reused across pages):
  - [ ] `Button` (primary/secondary + chunky hover/lift + focus states)
  - [ ] `Card` (2px charcoal borders)
  - [ ] `SectionHeader`
  - [ ] `FormInput` / `Textarea` (label + error/help text pattern)
  - [ ] `Badge` (Spicy/Vegan + New/Hot/Deal; angled deal style)
  - [ ] `Testimonial` / `ReviewCard`
- [ ] Build demo-specific components:
  - [ ] `PlatformStrip.astro` (UberEats/DoorDash/Menulog)
  - [ ] `DealsCarousel.astro` (horizontal scroll + "Limited time" label)
  - [ ] `MenuCategoryNav.astro` (jump links; sticky on scroll)
  - [ ] `MenuCard.astro` (name, description, price, spicy/vegan icons, "Quick Add" link)
  - [ ] `BestSellersGrid.astro` (top 4)
  - [ ] `HoursAndLocation.astro` (hours + pickup/location info; map placeholder)

## Phase 4 - Content & Data Layer

- [ ] Create `src/data/menu.json` with:
  - [ ] Categories: Pizza, Sides, Drinks, Desserts
  - [ ] Items: `id`, `name`, `description`, `price`, `tags`, `image`
  - [ ] Tags: "Spicy", "Vegan", "Best Seller" (as needed)
- [ ] Create `src/data/deals.json` with specials (e.g., "2 Large + Sides for $45") + platform links.
- [ ] Add realistic sample items and deals (enough to populate Home/Menu/Deals).
- [ ] Add sample reviews + rating used on Home/Deals (trust signals).
- [ ] Add NAP content used site-wide (footer + contact + schema).

## Phase 5 - Pages (Demo IA + Required Pages)

### Home (`src/pages/index.astro`)

- [ ] Hero: H1 + dual CTAs (Call + Order Online) above the fold.
- [ ] Platform strip section.
- [ ] Deals carousel section.
- [ ] Best sellers grid section (top 4 pizzas).
- [ ] Local trust: reviews + "Trusted by locals in Northbridge & Highgate."
- [ ] Areas we serve: Northbridge, Highgate, Maylands, Inglewood, Mount Hawthorn (natural language).
- [ ] Footer: hours + pickup instructions + parking availability.

### Menu (`src/pages/menu/index.astro` or `src/pages/menu.astro`)

- [ ] Sticky category nav (Pizza/Sides/Drinks/Desserts) with smooth anchor scrolling.
- [ ] Render full menu from `menu.json` by category.
- [ ] Dietary/heat tags displayed with accessible text (spicy/vegan icons + labels).
- [ ] "Quick Add" links route to the selected delivery platform.

### Deals (`src/pages/deals/index.astro`)

- [ ] Render all specials from `deals.json`.
- [ ] "Limited Time" countdown indicators (static text).

### Required pages from base prompt

- [ ] About (`src/pages/about.astro`) - brand story and "street-food premium" positioning.
- [ ] Services (`src/pages/services.astro` or equivalent) - catering, group orders, events.
- [ ] Contact (`src/pages/contact/index.astro`) - NAP + hours + phone links + map placeholder + contact form UI.
- [ ] Privacy (`src/pages/privacy.astro`) - simple legal page.
- [ ] Local SEO/GEO page (choose one):
  - [ ] Create a dedicated page (e.g., `src/pages/areas-we-serve.astro`), OR
  - [ ] Ensure Home includes robust Perth-targeted content beyond a suburb list

## Phase 6 - SEO (Global + Perth GEO)

- [ ] Page titles follow a consistent template (per-page + brand).
- [ ] Meta description per page (unique, conversion-focused).
- [ ] Canonical URLs set correctly (respecting `site` + `base`).
- [ ] OpenGraph: title/description + placeholder OG image.
- [ ] Twitter card meta.
- [ ] Add JSON-LD (FoodEstablishment / Restaurant) including:
  - [ ] `addressLocality: "Perth"`, `addressRegion: "WA"`, `addressCountry: "AU"`
  - [ ] `openingHours`, `priceRange`, `servesCuisine`, telephone, URL
  - [ ] `hasMenu` and/or menu URL (as appropriate)
- [ ] Add `robots.txt`.
- [ ] Add sitemap (if straightforward) and verify it works with the configured `site`.
- [ ] Internal linking: Home -> Menu -> Deals with clear CTAs (and back).

## Phase 7 - Accessibility & UX Checks

- [ ] One H1 per page; heading order is logical.
- [ ] Skip link works and is visible on focus.
- [ ] Keyboard navigation works across header, CTAs, carousels, menu anchors, and forms.
- [ ] Touch targets are large enough for mobile.
- [ ] Contrast is sufficient for all text and CTAs.
- [ ] Menu is accessible within 1 tap from Home on mobile.
- [ ] Sticky elements do not obscure content (especially the bottom bar and menu nav).

## Phase 8 - Performance

- [ ] Use `astro:assets` for images where possible; responsive sizes + lazy loading.
- [ ] Avoid heavy JS (keep carousel/jump-nav lightweight).
- [ ] Any motion enhancements are subtle and disabled/reduced for `prefers-reduced-motion`.

## Phase 9 - Deployment & Handoff

- [ ] Add build/run instructions (README or `/docs/`):
  - [ ] `npm install`
  - [ ] `npm run dev`
  - [ ] `npm run build`
  - [ ] `npm run preview`
- [ ] Verify the built site works under the GitHub Pages base path (no broken links/assets).
- [ ] Quick QA pass:
  - [ ] Mobile bottom bar CTAs (tel + platform)
  - [ ] Menu anchors + sticky nav behavior
  - [ ] Deals carousel scroll + cards
  - [ ] Basic SEO meta presence (view-source)

## Optional / Bonus

- [ ] "Open now / Closed" indicator based on hours.
- [ ] Sticky mobile "Order" CTA button on long pages (keep it unobtrusive).
- [ ] FAQ accordion (only if it supports conversion; keep JS minimal).

