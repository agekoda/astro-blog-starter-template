# designedbykoda

Source for [designedbykoda.com](https://designedbykoda.com) — a portfolio of custom PCB / ESP32 hardware, RF tools, and other builds. Built with [Astro](https://astro.build) and deployed on Cloudflare Workers as a static site.

## Project structure

```
src/
├── components/
│   ├── BackgroundFX.astro     dotted-grid + glow background, used on every page
│   ├── ProjectImage.astro     image with automatic "photo coming soon" placeholder
│   ├── ProjectCard.astro      project preview card (used on home + /projects)
│   ├── Header.astro / Footer.astro
│   └── ...
├── layouts/
│   ├── Layout.astro           shared shell (head, header, background, footer)
│   ├── ProjectLayout.astro    project detail page layout (hero, tags, gallery)
│   └── BlogPost.astro         layout for the stock /blog demo pages
├── content/
│   ├── projects/              ← one .md file per project, shows up on the site
│   └── blog/                  stock demo blog posts from the Astro starter
├── pages/
│   ├── index.astro            homepage — hero + full project grid
│   ├── about.astro
│   ├── projects/
│   │   ├── index.astro        full project listing, grouped by category
│   │   └── [...slug].astro    renders each project/*.md as its own page
│   └── blog/                  stock demo blog (not linked in nav)
└── styles/global.css          dark theme, shared across the whole site
```

## Adding a new project

Create a new file in `src/content/projects/`, e.g. `src/content/projects/my-new-thing.md`:

```md
---
title: "My New Thing"
tagline: "One sentence describing it"
description: "SEO/meta description, one or two sentences."
category: "RF & Wireless" # or "Smart Home" | "Portable & Wearable" | "Game"
status: "Complete" # or "Upcoming"
order: 14 # controls sort order, lower = earlier
heroImage: "/images/projects/my-new-thing/hero.jpg"
gallery:
  - "/images/projects/my-new-thing/1.jpg"
  - "/images/projects/my-new-thing/2.jpg"
---

Intro paragraph about the project.

## Hardware

- Part one
- Part two

## Features

- Thing it does
- Another thing it does
```

That's it — it'll automatically show up on the homepage, the `/projects` listing (grouped under its `category`), and get its own page at `/projects/my-new-thing/`. Use `##` headings in the body for sections (Hardware, Features, Firmware, etc.) — they're styled automatically.

## Adding photos

Every project already has a matching folder under `public/images/projects/<slug>/` and its frontmatter already points at the expected file paths (`hero.jpg`, `1.jpg`, `2.jpg`, ...). Until those files exist, the site automatically shows a clean "Photo coming soon" placeholder instead of a broken image — nothing to configure.

To add real photos:

1. Drop image files into `public/images/projects/<slug>/`, matching the filenames already referenced in that project's frontmatter (or update the frontmatter paths if you'd rather rename them).
2. That's it — no code changes needed. The placeholder swaps for the real photo automatically once the file resolves.

Recommended: `.jpg` or `.webp`, roughly 1600px wide for hero images is plenty.

## Commands

All commands are run from the root of the project, from a terminal:

| Command                           | Action                                           |
| :--------------------------------- | :------------------------------------------------ |
| `npm install`                      | Installs dependencies                             |
| `npm run dev`                      | Starts local dev server at `localhost:4321`       |
| `npm run build`                    | Builds the production site to `./dist/`           |
| `npm run preview`                  | Preview the build locally via `wrangler dev`      |
| `npm run check`                    | Type-checks + dry-run deploy check                |
| `npm run deploy`                   | Deploy to Cloudflare Workers                       |

## Deployment

This repo deploys to Cloudflare Workers via `wrangler`. Config lives in `wrangler.json`. If you've connected this repo to Cloudflare Pages/Workers for git-based deploys, pushing to the main branch will trigger a new deployment automatically — otherwise run `npm run deploy` locally.

## Credit

Originally scaffolded from the [Astro Blog Starter Template](https://github.com/withastro/astro/tree/main/examples/blog) / Cloudflare's Astro template, restyled and rebuilt as a project portfolio.
