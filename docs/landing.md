# Landing page

Static HTML landing page lives at `landing/index.html`. This is the drop-in target for marketing pages.

## Workflow

1. Replace `landing/index.html` with the desired HTML.
2. Co-locate any assets (images, CSS, JS) under `landing/assets/`.
3. To serve from Shopify, copy the HTML into a theme template or a Shopify Page via the admin / Pages API.
4. To serve standalone, host the `landing/` directory on any static host (GitHub Pages, Netlify, Vercel).
