# Blog

Personal blog built with [Eleventy](https://www.11ty.dev/) (11ty), automatically
deployed to GitHub Pages via GitHub Actions.

## Local development

```bash
npm install
npm run serve
```

The site is served at `http://localhost:8080` with live reload.

## Production build

```bash
npm run build
```

The output is generated in `_site/`.

## Adding a post

Create a Markdown file in `src/posts/`, for example `src/posts/my-post.md`:

```markdown
---
title: "Post title"
date: 2026-01-01
description: "Short summary of the post."
---

Post content in Markdown.
```

The post automatically appears on the home page, sorted by date.

## Deployment (GitHub Pages)

Deployment is automated via the
[`.github/workflows/deploy.yml`](.github/workflows/deploy.yml) workflow on every
push to the `main` branch.

**One-time setup required on GitHub:**

1. Go to **Settings → Pages** in the repository.
2. Under **Build and deployment → Source**, select **GitHub Actions**.
3. Merge/push to `main`: the site builds and publishes automatically at
   `https://<username>.github.io/<repo-name>/`.

The `pathprefix` used during the build is computed automatically from the
repository name, so no extra configuration is needed if the repo is renamed.

## Structure

```
src/
  _data/metadata.js   # site title, description, author
  _includes/           # layouts (base.njk, post.njk)
  posts/               # blog posts (Markdown)
  css/style.css        # styles
  index.njk            # home page (post list)
  about.md             # "about" page
eleventy.config.js      # Eleventy configuration
```
