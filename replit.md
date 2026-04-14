# LORE Store — Salla-Compatible Theme Foundation

## Overview

LORE is a premium e-commerce storefront for movie and TV show inspired phone cases and stickers. The project is intentionally structured to mirror a real **Salla Twilight theme**, making migration from this React/Vite preview straightforward.

## Stack

- **Framework**: React + Vite + Tailwind CSS + shadcn/ui
- **Routing**: wouter
- **Animations**: framer-motion / tw-animate-css
- **Fonts**: Playfair Display (serif headings), Outfit (body)
- **Monorepo**: pnpm workspaces

## Salla-Compatible Folder Structure

```
artifacts/lore-store/
├── twilight.json              ← Salla theme manifest (sections, settings schema, templates)
├── README.md                  ← Salla migration guide
└── src/
    ├── config/settings.json   ← Maps to Salla config/settings_data.json
    ├── layouts/
    │   └── DefaultLayout.tsx  ← Maps to Salla layouts/master.twig
    ├── sections/              ← Each file = one Salla theme section
    │   ├── HeroSection.tsx
    │   ├── FeaturedCategoriesSection.tsx
    │   ├── NewArrivalsSection.tsx
    │   ├── BrandBannerSection.tsx
    │   ├── BestSellersSection.tsx
    │   └── CollectionsSection.tsx
    ├── components/
    │   ├── layout/Navbar.tsx  ← Maps to Salla components/header.twig
    │   ├── layout/Footer.tsx  ← Maps to Salla components/footer.twig
    │   └── shop/ProductCard.tsx ← Maps to Salla components/product-card.twig
    ├── pages/                 ← Maps to Salla templates/*.twig
    │   ├── Home.tsx           ← templates/index.twig
    │   ├── Shop.tsx           ← templates/collection.twig
    │   ├── ProductDetail.tsx  ← templates/product.twig
    │   ├── Collection.tsx     ← templates/collection.twig (filtered)
    │   └── About.tsx          ← templates/page.twig
    └── data/products.ts       ← PLACEHOLDER: replaced by Salla product variables
```

## Pages & Routes

- `/` — Home (composing 6 independent sections)
- `/shop` — Product grid with category/search filters
- `/product/:id` — Product detail with variants, add to cart, related products
- `/collections/:slug` — Collection pages (sitcom, fantasy, mystery, etc.)
- `/about` — Brand story

## Brand Colors (→ twilight.json settings)

- Primary: `#3D1054` (deep purple)
- Background: `#F5F0E8` (soft cream)
- Accent: `#C9B8D8` (lavender)
- Foreground: `#1A0A2B`

## Key Commands

- `pnpm --filter @workspace/lore-store run dev` — start dev server
- `pnpm --filter @workspace/lore-store run build` — production build

## Salla Migration

See `artifacts/lore-store/README.md` for the full step-by-step guide, including:
- Exact variable mapping table (React → Salla Liquid)
- File-by-file conversion instructions
- GitHub push instructions
- How to fix the Salla GitHub connection error
