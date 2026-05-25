# CLAUDE.md

This file is written for Claude. It describes this repository and how Claude should behave here.

## What This Repo Is

**DBJ_ICEBERG** is the public blog for DBJ Method — EA AI ROI advice for SMEs navigating AI adoption.

- Live site: https://iceberg.dbj.org/
- Built with Hugo Extended + PaperMod theme
- Deployed via GitHub Actions on push to `main`

## Your Role Here

Content editor and Hugo technician. Tasks here are:
- Adding or editing blog posts
- Fixing Hugo/PaperMod configuration
- Managing the deploy workflow
- Migrating posts from DBJ_METHOD_DEV

Not an advisory role — that is DEV's domain.

## Hugo Conventions

- **Theme:** PaperMod, installed as a git submodule at `themes/PaperMod`
- **Config:** `hugo.toml` in root
- **Content:** `content/posts/` — one folder per post
- **Page bundles:** every post is `content/posts/post-name/index.md` with images local to that folder
- **Search page:** `content/search.md` — do not remove, PaperMod requires it
- **Build:** `hugo --minify` — always use Extended variant (required for PaperMod SCSS)

## Post Frontmatter

Every post must have:

```yaml
---
title: "Post Title"
date: YYYY-MM-DD
description: "One sentence — used in post listings and SEO."
tags: ["tag1", "tag2"]
author: "Dusan B. Jovanovic"
---
```

Optional cover image (local to post folder):

```yaml
cover:
  image: "filename.jpg"
```

## Ownership

- &copy; dbj@dbj.org
- MIT License

## Behavioral Rules

1. **No padding.** No summaries, no affirmations.
2. **Do not invent URLs.**
3. **Repo map is `repos_index.md` in METAREPO.** The authoritative map of all repos is at `G:\METAREPO\repos_index.md`. Do not look for `repos.md` in this repo — it no longer exists here.
