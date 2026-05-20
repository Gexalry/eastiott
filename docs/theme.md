# Theme

A minimal Shopify Online Store 2.0 theme skeleton lives in `theme/`. Designed to be the easiest possible starting point — small file count, no build step.

```
theme/
├── layout/theme.liquid          # Root HTML wrapper
├── templates/index.liquid       # Home page template (JSON)
├── sections/main-index.liquid   # Home hero section
├── snippets/                    # Reusable Liquid partials
├── assets/base.css              # Base styles
├── config/settings_schema.json  # Theme editor settings
└── locales/en.default.json      # Translations
```

## Modifying

1. Edit Liquid/CSS files locally.
2. Push to this branch.
3. Sync to Shopify either via the Shopify CLI (`shopify theme push`) or by uploading a zip in the Shopify admin.

## Notes

- Templates use the JSON template format (Online Store 2.0) so sections can be rearranged in the theme editor.
- For richer starting points, Shopify's [Dawn](https://github.com/Shopify/dawn) theme is the recommended reference — pull pieces from it as needed.
