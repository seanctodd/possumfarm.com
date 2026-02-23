# 🦝 POSSUM FARM — Official Website Repository

> *"I didn't know I needed a website for my possum farm. Then I got one. My life has been transformed."*
> — Papi Possum, Founder

---

## What Is This

This is the source code for [possumfarm.com](https://possumfarm.com), the official digital home of **Possum Farm** — the world's only certified organic, free-range, spiritually-awakened possum operation.

Founded in 2003 by the legendary **Papi Possum** after a possum named Bernadette climbed onto his porch railing, stared at him with ancient wisdom, and ate half his sandwich.

The rest is history.

---

## Technical Stuff (For The Non-Possums)

This site is built with **[Hugo](https://gohugo.io/)** — a blazing-fast static site generator that Papi chose primarily because it was fast and also because the logo looks a bit like a possum if you squint.

**Theme:** `possumfarm` — a fully custom theme built in the proud tradition of 2000s WordArt aesthetics, animated GIF energy, and the kind of websites that had visitor counters and used the word "WELCOME" in impact font.

**Stack:**
- Hugo (static site generator)
- Pure CSS (no frameworks, just chaos)
- Google Fonts (Fredoka One, Permanent Marker, Press Start 2P, Pacifico)
- Possum energy (not a real technology but it helps)

---

## Local Development

**Requirements:**
- [Hugo Extended](https://gohugo.io/installation/) v0.100.0 or later (just get the latest, Papi doesn't care)
- Git (for cloning and general git activities)
- A fondness for possums (optional but recommended)

**Get started:**

```bash
# Clone the repo
git clone https://github.com/seanctodd/possumfarm.com.git
cd possumfarm.com

# Start the local dev server
hugo server

# Open your browser to:
# http://localhost:1313
```

The server has live reload enabled, so when you save a file, the browser updates automatically. Papi calls this "magic" and refuses to accept a technical explanation.

**Build for production:**

```bash
hugo
```

Output lands in `public/`. That's the stuff you deploy.

**Create a new blog post:**

```bash
hugo new posts/my-great-possum-post.md
```

**Create a new store product:**

```bash
hugo new store/my-new-merch-item.md
```

---

## Project Structure

```
possumfarm.com/
├── hugo.toml              # Site config (baseURL, title, menu, etc.)
├── content/
│   ├── _index.md          # Homepage content
│   ├── about/             # About Papi page
│   ├── posts/             # Blog posts (Papi's dispatches from the farm)
│   └── store/             # Merch product pages
├── themes/possumfarm/
│   ├── layouts/           # HTML templates
│   │   ├── _default/      # baseof.html, list.html, single.html
│   │   ├── store/         # Store-specific list and single templates
│   │   └── about/         # About page layout
│   └── static/
│       ├── css/style.css  # The whole vibe
│       └── images/        # Theme images (possum logo SVG)
└── archetypes/            # Templates for hugo new commands
```

---

## Deploying to Cloudflare Pages

Cloudflare Pages is Papi's deployment platform of choice. It is free, fast, and has never once judged Papi for his life choices. Here's how to set it up:

### First-Time Setup

**Step 1: Push your code to GitHub**

Make sure your repo is on GitHub. If it isn't, Papi is disappointed but will help anyway:

```bash
git remote add origin https://github.com/YOUR_USERNAME/possumfarm.com.git
git branch -M main
git push -u origin main
```

**Step 2: Connect to Cloudflare Pages**

1. Go to [dash.cloudflare.com](https://dash.cloudflare.com) and log in (or create a free account)
2. Navigate to **Workers & Pages** → **Pages**
3. Click **Connect to Git**
4. Authorize Cloudflare to access your GitHub account
5. Select your `possumfarm.com` repository
6. Click **Begin setup**

**Step 3: Configure the build settings**

On the build configuration screen, use these exact settings:

| Setting | Value |
|---|---|
| **Production branch** | `main` |
| **Framework preset** | `Hugo` |
| **Build command** | `hugo` |
| **Build output directory** | `public` |
| **Root directory** | *(leave blank)* |

**Step 4: Set Hugo version (important!)**

Hugo version matters. Set an environment variable so Cloudflare uses the right one:

Under **Environment variables (advanced)**, add:

| Variable name | Value |
|---|---|
| `HUGO_VERSION` | `0.123.7` |

Click **Save and Deploy**.

**Step 5: Watch it build**

Cloudflare will now pull your code, build it with Hugo, and deploy it to a `*.pages.dev` subdomain. This usually takes about 60 seconds, which is ample time to go check on the possums.

### Setting Up Your Custom Domain

1. In your Cloudflare Pages project, go to **Custom domains**
2. Click **Set up a custom domain**
3. Enter `possumfarm.com`
4. Follow the DNS instructions (if your domain is already on Cloudflare, this is automatic and magical)
5. Also add `www.possumfarm.com` if you want both versions to work

Cloudflare handles the SSL certificate automatically. Papi didn't have to do anything. He considers this a miracle.

### Ongoing Deployments

Every time you push to `main`, Cloudflare Pages automatically rebuilds and deploys the site. No additional configuration required.

```bash
# Make your changes, then:
git add .
git commit -m "added more possum content as is my right"
git push
```

That's it. The possums will be live on the internet within approximately one minute.

**Preview deployments:** Every pull request also gets its own preview URL, so you can review changes before merging. Papi doesn't use pull requests because he works alone and answers to no one except Bernadette.

---

## Adding Merch to the Store

Products are just Markdown files in `content/store/`. Each product uses these front matter fields:

```yaml
---
title: "Product Name"
date: 2024-01-01
draft: false
price: "29.99"
emoji: "🦝"          # The product's display emoji (big impact)
variants: ["S", "M", "L"]  # Size/option variants (optional)
tags: ["apparel"]
description: "One-line description for SEO and store listings"
---

Long-form product description in Markdown goes here.
```

Papi writes all product descriptions himself. He insists. Do not argue with him about this.

---

## Content Guidelines

- All blog posts should be authored by `Papi Possum`
- All possum facts should be real possum facts (Papi has standards)
- The tone is: eccentric, warm, unhinged in a specific and intentional way
- Do not write anything mean about possums. They will not read it but Papi will and he will be upset.
- Bernadette is to be treated with the dignity befitting a 21-year-old possum legend

---

## License

MIT License. Do whatever you want with the code. Papi is a generous man.

The possums are not included in the license. They are their own beings.

---

*🦝 Built with love, coffee, and the guidance of Bernadette*

*Possum Farm — Est. 2003 — Play Dead, Live Free*
