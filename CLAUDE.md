# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Hugo static site for [possumfarm.com](https://possumfarm.com) — an organic free-range possum farm run by the eccentric Papi Possum. Custom theme (`possumfarm`) with 2000s WordArt aesthetic. Deployed via Cloudflare Pages.

## Common Commands

```bash
# Start local dev server with live reload (http://localhost:1313/)
hugo server

# Build for production (outputs to public/)
hugo

# Build with drafts
hugo -D

# New blog post
hugo new posts/my-post.md

# New store product
hugo new store/my-product.md
```

## Architecture

- **`hugo.toml`** — site config (baseURL, title, menu items, site params)
- **`content/posts/`** — Markdown blog posts by Papi Possum
- **`content/store/`** — Merch product pages (price, emoji, variants front matter)
- **`content/about/`** — About Papi page (uses `about/single.html` layout)
- **`themes/possumfarm/`** — Fully custom theme; do not use external themes
  - `layouts/_default/` — `baseof.html`, `list.html`, `single.html`
  - `layouts/store/` — Store-specific list and single templates
  - `layouts/about/` — About page layout
  - `static/css/style.css` — All CSS (2000s WordArt aesthetic, CSS variables, dark bg)
  - `static/images/possum.svg` — Site logo possum
- **`archetypes/store.md`** — Template for `hugo new store/` with store-specific front matter

## Store Product Front Matter

```yaml
---
title: "Product Name"
price: "29.99"
emoji: "🦝"
variants: ["S", "M", "L"]
tags: ["apparel"]
description: "Short description"
---
```

## Theme CSS Variables

Defined in `:root` in `style.css`: `--possum-purple`, `--possum-pink`, `--possum-green`, `--possum-yellow`, `--possum-orange`, `--possum-teal`, `--dark-bg`, `--card-bg`, `--card-border`.

## Git Submodule

No git submodules — custom theme lives directly in `themes/possumfarm/`.

## Deployment

Cloudflare Pages auto-deploys on push to `main`. Build command: `hugo`. Output directory: `public`. Set `HUGO_VERSION=0.123.7` in Cloudflare env vars.
