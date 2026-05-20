# Products

Products are managed in Shopify and accessed via MCP.

## Common operations

| Action | Tool |
| --- | --- |
| Search | `search_products` |
| Read one | `get-product` |
| Create | `create-product` |
| Update | `update-product` |
| Bulk status change | `bulk-update-product-status` |
| Inventory | `get-inventory-levels`, `set-inventory` |

For anything not covered above (metafields, variants beyond basics, gift cards, etc.) fall back to `graphql_query` / `graphql_mutation`.

## Conventions

- SKUs follow `EAST-<category>-<short>` (TBD — update once first products land).
- Product copy lives in Shopify; do not duplicate it into this repo.
