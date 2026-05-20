# eastiott

Repository backing the Shopify store **My Store** (`7rkgkh-kh.myshopify.com`).

Organized using the [llms.txt](https://llmstxt.org) convention — see [`llms.txt`](./llms.txt) for the navigable index.

## Layout

```
.
├── llms.txt              # LLM-navigable index (start here)
├── docs/                 # Markdown docs per resource type
├── theme/                # Minimal Shopify theme skeleton
└── landing/              # Static HTML landing page workspace
```

## Quick start

- Drop landing-page HTML into `landing/index.html`.
- Modify the theme under `theme/` (Liquid).
- Use the Shopify MCP server for store management (products, collections, orders, inventory, analytics).
