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

From the repo root:

```
shopify theme push --unpublished --store 7rkgkh-kh.myshopify.com
```

The theme directories (`assets/`, `config/`, `layout/`, `locales/`, `sections/`, `snippets/`, `templates/`) live at the branch root so the Shopify CLI and the GitHub theme integration both treat the branch as a valid theme. (Requires Shopify CLI auth — not handled by this repo.)

## Run analytics

Use `run-analytics-query` with a ShopifyQL query, e.g.

```
FROM sales SHOW total_sales SINCE -30d
```
