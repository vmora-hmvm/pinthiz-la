# PINTHIZ.LA WEBSITE TEMPLATE BLUEPRINT
# How to Recreate This Site for Any Business

This document is a complete blueprint of the pinthiz.la website structure. Give this to an AI agent along with a new company's branding info, and it can recreate the entire site in the same format.

---

## SITE ARCHITECTURE

The site is a **single HTML file** (`index.html`) — no backend, no database, no frameworks. Everything lives in one file:
- All CSS in `<style>` tags at the top
- All HTML in `<body>`
- All JavaScript in `<script>` tags at the bottom
- Deployed free via GitHub Pages

### Section Order (top to bottom):
1. **NAV** — Sticky header with logo, links, search, cart icon
2. **HERO** — Full-screen hero with background image, headline, CTA buttons
3. **SHOP** — Product grid with category filters, featured carousel, search, pagination
4. **STORY / FOUNDER** — Two-column layout: photo + bio text
5. **PROMO + GALLERY** — Tag-to-Save promo banner + auto-scrolling community gallery
6. **RAFFLE WHEEL** — Interactive spin wheel with entry form
7. **UPDATES** — Blog-style cards for raffles, pop-ups, giveaways
8. **UPCOMING GAMES** — Game/event schedule cards
9. **SHIPPING** — Expandable shipping info cards
10. **FAQ** — Accordion-style FAQ
11. **SHARE SECTION** — Social share prompt
12. **FOOTER** — Logo, Instagram CTA, checkout button, copyright
13. **BIRTHDAY SURPRISE** (optional) — Hidden birthday section with photos
14. **CART DRAWER** — Slide-out cart with Venmo/Zelle/Stripe checkout
15. **PRODUCT MODAL** — Click-to-expand product detail popup

---

## BRANDING VARIABLES (swap these)

At the top of the `<style>` section, CSS variables control the entire color scheme:

```css
:root{
  --navy:#0B1628;
  --navy-mid:#0f1e36;
  --navy-light:#1a2a47;
  --blue:#005A9C;
  --blue-bright:#1E90FF;
  --gold:#CBA135;
  --gold-bright:#F5D76E;
  --cream:#E8DCC6;
  --muted:#6b7c9a;
  --glass-border:rgba(255,255,255,.08);
}
```

### To rebrand for a new company:
1. Replace all 6 color variables with the new brand's palette
2. Swap logo image URLs (nav, hero, footer)
3. Change font imports (Google Fonts link in `<head>`)
4. Update all text content (headlines, taglines, descriptions)
5. Replace product images and product data array
6. Swap background images for each section
7. Update Instagram/social links
8. Update payment methods (Venmo, Zelle, Stripe)

---

## PRODUCT DATA STRUCTURE

Products are defined in a JavaScript array. Each product is one line:

```javascript
const PRODUCTS = [
  {id:1, name:"Product Name", cat:"pin", price:12, img:"URL_TO_IMAGE", caption:"Short Name", desc:"Description text here.", featured:true},
];
```

### Fields:
| Field | Type | Description |
|-------|------|-------------|
| `id` | number | Unique ID (1, 2, 3...) |
| `name` | string | Full product name shown on card |
| `cat` | string | Category: "pin", "sticker", "shirt", "patch" |
| `price` | number | Price in dollars (no $ symbol) |
| `img` | string | Full URL to product image (transparent PNG recommended) |
| `caption` | string | Short label (shown in modal/quick view) |
| `desc` | string | Longer description for product modal |
| `featured` | boolean | true = appears in top carousel, false = grid only |

### Categories must match filter buttons:
```html
<button class="filter-btn active" data-cat="all">All</button>
<button class="filter-btn" data-cat="pin">Pins</button>
<button class="filter-btn" data-cat="sticker">Stickers</button>
```

---

## KEY FEATURES TO REPLICATE

### 1. Product Grid + Featured Carousel
- Featured products (featured:true) auto-populate a horizontal carousel at the top
- All products populate a responsive grid (4 cols desktop, 2 cols mobile)
- Pagination shows 12 products per page
- Real-time search filters by name/caption as you type
- Category filter buttons show/hide products by cat field

### 2. Cart System
- Click "+" on any product to add to cart
- Cart count badge appears on nav icon
- Slide-out drawer shows items with quantity controls
- Three checkout options: Venmo, Zelle, Stripe (all show alert popups)
- Cart data stored in browser localStorage (survives page refresh)

### 3. Raffle Wheel
- SVG-based spinning wheel with 8 segments
- Entry form with quantity selector (1/3/5/10 entries)
- Tiered pricing: 1 entry=$5, 3=$12, 5=$20, 10=$35
- On submit: adds raffle to cart, shows confirmation
- Confetti animation fires on entry

### 4. Community Gallery
- Auto-scrolling horizontal carousel
- Pauses on hover
- Infinite loop (first images repeat at end)
- Uses CSS animation, no JavaScript needed for scrolling

### 5. Promo/Tag-to-Save Section
- Three-step promo instructions in pill-shaped cards
- "Follow, Tag, Share" format
- Background image with dark overlay

### 6. FAQ Accordion
- Click question to expand/collapse answer
- Pure JavaScript toggle, no libraries
- "+" icon rotates when open

### 7. Shipping Cards
- Expandable cards (click to open/close)
- Four cards: US Shipping, International, Local Pickup, Specialty
- Each has icon + title + description

### 8. Birthday Section (optional)
- Two-column layout: text + photo slideshow
- Auto-rotating photo slideshow with dots indicator
- Balloon and confetti CSS animations
- Can be removed entirely if not needed

---

## REBRANDING CHECKLIST

When adapting this template for a new company:

### A. Colors and Fonts
- [ ] Replace all CSS variables in :root with new brand colors
- [ ] Replace Google Fonts link in head with new font choices
- [ ] Update color usage throughout (gradients, shadows, borders)

### B. Logo and Images
- [ ] Replace nav logo (nav-logo img src)
- [ ] Replace hero background image
- [ ] Replace story section founder photo
- [ ] Replace gallery images (community photos)
- [ ] Replace raffle section background image
- [ ] Replace footer logo
- [ ] Replace birthday photos (if using)
- [ ] Replace all product images in PRODUCTS array

### C. Text Content
- [ ] Update title tag and meta description
- [ ] Replace hero headline and subtext
- [ ] Update nav links text (keep same section IDs)
- [ ] Replace story section bio text
- [ ] Replace promo section instructions
- [ ] Update raffle section title/description
- [ ] Update blog/updates cards
- [ ] Update game/event schedule
- [ ] Replace all shipping info text
- [ ] Replace all FAQ questions and answers
- [ ] Update footer text and copyright year
- [ ] Replace birthday text (or remove section)

### D. Functional Updates
- [ ] Update PRODUCTS array with new products
- [ ] Update category filter buttons to match new product types
- [ ] Update Venmo handle in checkout function
- [ ] Update Zelle email in checkout function
- [ ] Set up Stripe account and replace Stripe checkout
- [ ] Update Instagram URL (nav, promo, footer)
- [ ] Update raffle pricing tiers if different
- [ ] Update shipping rates and policies

### E. Remove/Replace Sports-Specific Elements
- [ ] Remove or replace "Upcoming Games" section with "Upcoming Events" or "Pop-Up Schedule"
- [ ] Remove or replace stadium organ sound effect
- [ ] Remove or replace baseball terminology in FAQ
- [ ] Remove or replace "Stadium Pickup" shipping option
- [ ] Replace stitch dividers if not on-brand
- [ ] Update raffle wheel segment text

---

## AI AGENT PROMPT TEMPLATE

When giving this to an AI agent to build a new site, use this prompt:

```
I have a single-page website template (pinthiz.la) that I want to recreate 
for [COMPANY NAME]. Here's what I need:

BUSINESS INFO:
- Name: [Company Name]
- Tagline: [tagline]
- Instagram: @[handle]
- Products: [type of products, categories, price points]
- Colors: [hex codes for primary, accent, background, text]
- Fonts: [font names from Google Fonts]
- Logo: [URL or description]
- Payment: [Venmo handle, Zelle email, Stripe yes/no]
- Shipping: [rates, pickup options]
- Special sections: [raffle? gallery? events? blog?]

KEEP THE SAME:
- Single-file HTML structure (CSS + HTML + JS in one file)
- Product grid with filters, search, pagination, featured carousel
- Cart drawer with quantity controls
- FAQ accordion
- Shipping expandable cards
- Responsive mobile layout
- Section-by-section animations

REPLACE:
- All colors, fonts, logos, images
- All text content
- Product data array
- Payment handles
- Social links
- Any sports-specific elements

Do NOT add orange to the color palette. Maintain a premium, million-dollar 
design standard. Every image should use absolute media.base44.com URLs.
```

---

## FILE STRUCTURE

```
pinthiz-la/
  index.html          <- EVERYTHING (CSS, HTML, JS in one file)
  README.md           <- This blueprint
  (no other files needed - all images hosted on media.base44.com)
```

## DEPLOYMENT

1. Create a GitHub repository (e.g., kandy-k-shop)
2. Upload index.html
3. Go to Settings, Pages, Source: main branch, Save
4. Site goes live at https://[username].github.io/[repo-name]/
5. Updates: push changes to main branch, site auto-updates in ~30 seconds

---

## IMPORTANT NOTES

- All image URLs must be absolute (https://media.base44.com/...) - relative paths cause 302 redirect errors on GitHub Pages
- The site is 100% static - no server, no database, no user accounts
- Cart data is stored in browser localStorage (cleared if user clears cache)
- Stripe checkout currently shows an alert placeholder - real Stripe requires backend functions
- The raffle wheel spin is decorative - real raffle entries go through the cart
- Search is real-time and case-insensitive, filtering by name and caption fields
- Mobile responsive breakpoint is 768px (CSS media queries)
