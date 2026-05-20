# Theme

Custom Online Store 2.0 theme for **Eastiott**, ported from the four reference HTMLs in `references/`.

## Brand system

Tokens live in `assets/eastiott.css`:

```
--blue       #006B95   primary — buttons, links, selected states
--blue-deep  #00567a   hover on primary
--slate      #4F5B65   dark neutral — body text, dark strips
--gold       #B3812A   accent — stars, dividers, kickers, hover underlines
--gold-soft  #c79a47   hover on gold
--red        #A01A1F   sale badge only (very sparing)
--paper      #f7f5f1   main background
--paper-2    #efece5   alt section background
--ink        #1c2227   headings
--line       rgba(79,91,101,.18)   hairlines
```

Typography is loaded once in `layout/theme.liquid` via Google Fonts:

- Display: **Cormorant Garamond** (400/500/600 + italic)
- Body / UI: **Jost** (300/400/500/600)

## Section map

| Section | Source HTML | Notes |
| --- | --- | --- |
| `main-product` | `references/eastiott-tote.html` (gallery + buy box) | Wired to real product/variant data. Bundle tiers + add-ons presentational. |
| `trust-strip` | `references/eastiott-tote.html` (slate stats row) | Stat blocks editable. |
| `editorial-feature` | `references/eastiott-tote.html` (2 editorial blocks) | Reusable; `reversed` + `alt_bg` toggles. |
| `featured-on` | `references/eastiott-tote.html` ("as admired in") | Placeholder names — flag to replace before publish. |
| `features-grid` | `references/eastiott-features-section.html` | Four feature blocks with image + body. |
| `product-specs` | `references/eastiott-tote.html` (specs table) | Block-driven; each row editable. |
| `trusted-by` | `references/eastiott-trusted-section.html` | Carousel with scoped JS (per-section id). |
| `rated-grid` | `references/eastiott-rated-section.html` | Wire the four blocks to the `eastiott-customer-*` Shopify files. |
| `faq` | `references/eastiott-tote.html` (FAQ accordion) | Scoped JS, single-open-at-a-time. |
| `newsletter` | `references/eastiott-tote.html` (newsletter) | Uses Shopify `{% form 'customer' %}` — real signups. |

Chrome sections rendered by `layout/theme.liquid`:

- `announcement-bar`
- `header`
- `footer`

## Templates

- `templates/product.json` — the PDP. Default template for any product. Section order:

  1. `main-product` (gallery + buy box)
  2. `trust-strip`
  3. `editorial-feature` (block 1)
  4. `featured-on`
  5. `features-grid` (the four features)
  6. `editorial-feature` (block 2, reversed + alt bg)
  7. `product-specs`
  8. `trusted-by`
  9. `rated-grid`
  10. `faq`
  11. `newsletter`

- `templates/index.liquid` — placeholder home (untouched from initial scaffold; brand sections can be dropped here too).

## Pre-publish guardrails

- Product status is **DRAFT** and inventory is **0** — switch to live with stock before publishing the theme.
- Reviews, the 4.8/5 star ratings, "12,500 reviews", and "as admired in" press names are all placeholders. **Replace with real data or wire a reviews app first** — fabricated verified reviews are an FTC/ASA problem.
- Bundle tiers and add-ons in the buy box are **presentational** — they do not modify cart contents. Wire to a real upsell / selling-plan integration before claiming bundle discounts.
- The buy-box price reads live from the selected variant. Reference HTML shows £59.99 sale pricing; that is **not** wired and will not appear unless the variant has a real compare-at price.

## Deploy / preview workflow

Theme writes from this session are blocked. To preview:

1. Pull this branch locally.
2. Authenticate the [Shopify CLI](https://shopify.dev/docs/themes/tools/cli) for `7rkgkh-kh.myshopify.com`.
3. From the repo root, push as an **unpublished** theme:

   ```
   shopify theme push --unpublished --store 7rkgkh-kh.myshopify.com
   ```

4. Use the preview URL Shopify returns. Publish from the Shopify admin only after review.

Alternative: zip the repo root (the `assets/`, `config/`, `layout/`, `locales/`, `sections/`, `snippets/`, `templates/` directories together) and upload via **Online Store → Themes → Add theme → Upload zip**. Shopify's GitHub theme integration also works on this branch — it requires the standard theme directories at the branch root, which is how this repo is laid out.

## Editing in the theme editor

All sections expose merchant-editable settings — copy, kickers, headings, blocks. Customers and quotes for `rated-grid` are blocks; press names for `featured-on` are blocks; FAQ items are blocks; trust-strip stats are blocks. Add/reorder in the theme editor without touching code.
