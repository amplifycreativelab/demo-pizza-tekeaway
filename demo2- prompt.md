# Developer Prompt: "Takeaway Express" Pizza Site (Astro)

Tasks checklist: `pizza-takeaway-demo/Demo 2 - Takeaway Express - Tasks.md`

## Project Overview

Build a high-conversion, "order-first" takeaway website for a Perth-based pizza shop using Astro 5.x. The site must be optimized for speed (Lighthouse 100s) and designed to drive two specific actions:

- Phone calls
- Delivery platform clicks (UberEats/DoorDash/Menulog)

## 1. Design System & Style Guidelines

The design must feel "Street-Food Premium" - energetic, bold, and appetizing. Avoid a "corporate" look.

### Color Palette

- Primary (Action): `#D92228` (Deep Tomato Red) - Used for primary CTAs and price points
- Background: `#FFFBF2` (Warm Cream) - The primary canvas to provide an artisanal feel
- Accent: `#F5A623` (Mustard Yellow) - For "New," "Hot," or "Deal" badges
- Text/Structure: `#1A1A1A` (Charcoal) - High-contrast headings and borders

### Typography

- Headings: Bold, condensed Sans-Serif (e.g., Archivo Black). Use uppercase for H1 and H2.
- Body: Highly legible Sans-Serif (e.g., Inter or Plus Jakarta Sans).

### UI Characteristics

- Punchy look: Use 2px solid charcoal borders on cards and buttons to create a "Neo-Brutalist" pop.
- Badges: 8-degree angled labels for deals to create visual energy.
- Buttons: Chunky buttons with a subtle hover state that "lifts" or changes color depth.

## 2. Core Features & Functionality

### A. Mobile-First Navigation

- Sticky bottom bar: A persistent UI element on mobile screens
  - Left half: Call Shop (tel link)
  - Right half: Order Online (primary red background, links to platform)
- Header: Minimalist. Logo on the left, "Menu" and "Deals" links, and a prominent "Order" button for desktop.

### B. Data-Driven Pages (Astro Content Collections or JSON)

- Data sources: `src/data/menu.json` and `src/data/deals.json`
- Categories: Pizza, Sides, Drinks, Desserts
- Menu cards must include: title, description, price, "Spicy" or "Vegan" icons, and a "Quick Add" (links to delivery platform)

### C. Page Structure

Home:

- Hero: Catchy H1: "Hot Pizza in 20 Mins. Perth's Best Slice." + dual CTA buttons
- Platform strip: logo marquee of UberEats, DoorDash, and Menulog
- Deals carousel: horizontal scroll of high-value offers (e.g., "2 Large + Sides for $45")
- Best sellers: grid of top 4 pizzas with high-quality images
- Local trust: review section + "Trusted by locals in Northbridge & Highgate."
- Footer: clear hours of operation, pickup instructions, and parking availability

Menu Page:

- Filterable by category
- Jump-links at the top for quick navigation

Deals Page:

- Dedicated list of all current specials with "Limited Time" countdown indicators (static text)

## 3. SEO & Local Optimization (Perth, WA)

Local keywords: Naturally integrate suburb mentions: Northbridge, Highgate, Maylands, Inglewood, and Mount Hawthorn.

Technical SEO:

- Implement FoodEstablishment JSON-LD schema in the `<head>`
- Include `openingHours`, `priceRange`, and `servesCuisine`
- Ensure all images have descriptive alt text (e.g., "Freshly baked pepperoni pizza in Northbridge, Perth")

## 4. Technical Stack Requirements

- Framework: Astro 5.x (SSR or Static, depending on hosting)
- Styling: Tailwind CSS
- Images: Use the `astro:assets` component for automatic WebP conversion and resizing
- Icons: Use `astro-icon` or Lucide icons

## 5. Sample Data Structure (`menu.json`)

```json
{
  "category": "Pizza",
  "items": [
    {
      "id": "pepperoni-classic",
      "name": "The Northbridge Pepperoni",
      "price": 24,
      "description": "Double pepperoni, mozzarella, and our signature spicy tomato base.",
      "tags": ["Spicy", "Best Seller"],
      "image": "/images/pizzas/pepperoni.jpg"
    }
  ]
}
```

