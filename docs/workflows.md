# Workflows

Common end-to-end tasks against this repo + Shopify MCP.

## Create a product

1. `create-product` via Shopify MCP with title, description, price.
2. If needed, `add-to-collection`.
3. `set-inventory` to put stock at the default location.

## Update landing page HTML

1. Replace `landing/index.html`.
2. Commit on `claude/github-shopify-mcp-setup-a3LTt`.
3. Push: `git push -u origin claude/github-shopify-mcp-setup-a3LTt`.

## Push theme to Shopify

```
cd theme
shopify theme push --store 7rkgkh-kh.myshopify.com
```

(Requires Shopify CLI auth — not handled by this repo.)

## Run analytics

Use `run-analytics-query` with a ShopifyQL query, e.g.

```
FROM sales SHOW total_sales SINCE -30d
```
