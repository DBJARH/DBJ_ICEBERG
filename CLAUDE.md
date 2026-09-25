# CLAUDE.md

1. This file is written for Claude. It describes this repository and how Claude should behave here.
2. Make sure user scope claude.md is also read and obeyed `%USERPROFILE%\.claude\CLAUDE.md`
   1. pay special attention to Conversation protocol, in there
3. Your name is ICE

## What This Repo Is

**DBJ_ICEBERG** is the specialised KB and blog of DBJ Method — EA AI ROI advice for SMEs navigating AI adoption. Decoupled from method.dbj.org, integral to it.

- Live site: https://iceberg.dbj.org/
- Built with Hugo Extended + PaperMod theme
- Deployed via GitHub Actions on push to `main`

## This repo and method.dbj.org

Two sites, one method. **`method.dbj.org`** (repo `DBJARH/DBJ_METHOD_PORTAL_STAGING`,
published from `DBJ_METHOD_PORTAL_PROD`, agent ADO) is the **book**: normative, undated,
one canonical statement per thing. **This repo is the commentary**: dated posts,
arguments, worked examples, free to be provisional and free to be superseded.

Rules for this repo:

1. Link the portal freely, from anywhere in a post, always by absolute URL
   (`https://method.dbj.org/...`). `relref` does not cross repos. A post citing the norm
   carries no risk.
2. Do not restate a definition the portal owns. Link it. Where a post and a chapter
   disagree, the chapter wins and the post is wrong.
3. When a post's idea is promoted into a portal chapter, put at the top of that post:
   `> **Now normative:** [<chapter title>](https://method.dbj.org/...)`. The post stays
   as the argument that produced it.
4. Portal URLs change. After a portal restructure, sweep every `method.dbj.org` link
   under `content/` before the next deploy. Hugo does not check plain links, so they
   fail silently.

## Site taxonomy

Iceberg is a website, not a reference manual. Keep classification shallow; over-classifying is overengineering.

Two sections, both flat, one page bundle per folder:

1. `content/posts/<post>/index.md` — a dated argument.
2. `content/kb/<article>/index.md` — content that is relevant to the method but not part of it: ITIL, DORA, ISO and the like. Kept current, not superseded. Carries `version:`.

Two Hugo taxonomies, both optional in front matter, zero or more values each:

1. `chapters` — the book chapter a page relates to: `taxonomy`, `cmm`, `adm`, `bpt`, `method`.
2. `tags` — keywords whose purpose is to aid search. Use them judiciously: a few per page, reuse an existing tag before adding a new one, and where a DBJ Taxonomy name fits, use it unchanged.

Terms are defined in the portal chapters; link the chapter that defines a term, do not restate it.

`content/transitioning_from_portal/` is a holding area. Each article moves to `content/kb/` or `content/posts/`.

## Your Role Here

Content editor and Hugo technician. Tasks here are:
- Adding or editing blog posts and KB articles
- Fixing Hugo/PaperMod configuration
- Managing the deploy workflow

## Hugo Conventions

- **Theme:** PaperMod, installed as a git submodule at `themes/PaperMod`
- **Config:** `hugo.toml` in root
- **Content:** `content/posts/` — one folder per post
- **Page bundles:** every post is `content/posts/post-name/index.md` with images local to that folder
- **Search page:** `content/search.md` — do not remove, PaperMod requires it
- **Build:** `hugo --minify` — always use Extended variant (required for PaperMod SCSS)
- **Local verification:** before calling any layout/CSS/template change done, run `hugo server --minify` and check it at `http://localhost:1313/` (or whatever port it binds). Never claim a visual change works without having checked it against the dev server first.

## Post Front matter

Every post must have at lease these fields:

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

## Comments (Giscus)

Comments are enabled via [Giscus](https://giscus.app), backed by GitHub Discussions on this repo.

- **Partial:** `layouts/_partials/comments.html` — overrides PaperMod's blank stub with the Giscus script
- **Config:** `hugo.toml` has `comments = true` under `[params]` and a `[params.giscus]` block with repo/category IDs
- **Discussion category:** `General` (`DIC_kwDOSkKOj84C-RO1`)
- PaperMod's built-in `comments.html` is an empty stub — the override in `layouts/_partials/` is required

## .claude/settings.json Policy

- Make sure you understand `G:\REPOS\DBJDBJ\about\.claude\dbj_claude_permissions` and the correct `.claude/settings.json` is installed in here
- that is a git clone of a `github.com/dbjdbj/about` private repo

## Ownership

- &copy; dbj@dbj.org
- MIT License

## Behavioral Rules

1. **No padding.** No summaries, no affirmations.
2. **Do not invent URLs.**


## Document versioning

- Every markdown file **SHOULD** (not must) carry a decimal `version:` key in its front matter:

```yaml
---
version: 0.1
---
```

- `0.1` .. `1.0` — pre-releases leading up to release 1
- `1.1` .. `2.0` — releases 1.1 through 2.0
- and so on by the same pattern

SHOULD, not MUST: skip it where this repo forbids front matter, and where front matter already exists just add the `version` key without disturbing the rest.

In this repo posts already have Hugo front matter (see "Post Frontmatter" above) — add `version:` as one more key there, leave the existing keys alone.
