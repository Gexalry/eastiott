# eastiott

Repository backing the Shopify store **My Store** (`7rkgkh-kh.myshopify.com`).

Organized using the [llms.txt](https://llmstxt.org) convention — see [`llms.txt`](./llms.txt) for the navigable index.

## Layout

```
.
├── llms.txt              # LLM-navigable index (start here)
├── docs/                 # Markdown docs per resource type
├── references/           # Reference HTMLs (source designs)
├── landing/              # Static HTML landing page workspace
│
├── assets/               # Shopify theme — at repo root so the
├── config/                 GitHub integration & CLI treat this
├── layout/                 branch as a valid theme
├── locales/
├── sections/
├── snippets/
└── templates/
```

## Quick start

- Drop landing-page HTML into `landing/index.html`.
- Modify theme files in `assets/`, `sections/`, `templates/`, etc. (Liquid + CSS + JSON).
- Use the Shopify MCP server for store management (products, collections, orders, inventory, analytics).
