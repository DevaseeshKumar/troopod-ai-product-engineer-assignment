# Purelane Shopify Homepage

Production Shopify implementation of the Purelane homepage prototype, built on Dawn. The five assignment sections are editable in the Shopify Theme Editor and use Shopify product data instead of hardcoded product content.

## Preview

https://purelane-development.myshopify.com/?preview_theme_id=162632794326

## What was built

- **Hero** — editable copy, calls to action, offer labels and three product selectors. When a Hero product has an image, the section uses its Shopify product image and live price.
- **Shop grid** — collection-driven product shelf with real product title, price, compare-at price, availability, variant add-to-cart and image fallback.
- **Best-selling combos** — repeatable blocks with a product list. A configured bundle product is used as the purchasable SKU and source of bundle price; otherwise the selected products are added together at their actual individual prices.
- **Bundles** — 2, 3 and 5 product tiers seeded in the homepage template. Each tier uses real selected product images and prices.
- **Reviews rail** — repeatable Theme Editor review blocks, with configurable rating, quote, author and product note.

## Theme Editor setup

1. Open **Online Store → Themes → Customize → Homepage**.
2. Select a collection for **Purelane Shop Grid**.
3. In Hero, select the product images used in the visual offers.
4. For each Combo or Bundle block, select its included products.
5. For a discounted combo/bundle, create a real Shopify product for that offer and select it in **Bundle product (recommended)**. Its product price and compare-at price are then displayed and it is the single product added to cart.

> A product list alone cannot create a discounted Shopify bundle price. Use a dedicated bundle product (or Shopify Bundles) when a specific bundle price is required.

## Optional product metafields

The theme works without metafields. These optional product metafields enhance product cards:

| Namespace and key | Type | Purpose |
| --- | --- | --- |
| `custom.badge` | Single line text | Product-card label, e.g. `Best seller` or `New` |
| `reviews.rating` | Number (decimal) | Rating shown on a product card, e.g. `4.8` |
| `reviews.rating_count` | Number (integer) | Review-count text shown beside the rating |

Create them under **Settings → Custom data → Products** in Shopify Admin. They are optional: the product grid still renders when they are not set.

## Test data to seed

Seed at least eight relevant products in the selected collection, including:

- one sold-out product;
- one product without an image (the grid shows an intentional `No image` fallback);
- one product with a long title.

## QA performed

- Shopify Theme Check: **0 errors**.
- JSON and section-schema validation.
- Responsive card-image constraints and no-image fallbacks.
- Native Shopify single-product and multi-item cart form payloads.

## Notes on the original prototype

The prototype used fixed product copy, prices and visual placeholders. This implementation keeps the visual system while replacing merchant-managed content with Theme Editor settings and Shopify product records. Product images, availability, prices and add-to-cart behaviour now come from Shopify.
