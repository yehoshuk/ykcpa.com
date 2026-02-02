# CLAUDE.md - AI Assistant Guide for ykcpa.com

## Project Overview

This is **ykcpa.com**, a personal blog/notes site built with [Eleventy (11ty)](https://www.11ty.dev/) static site generator, based on the [Hylia](https://github.com/hankchizljaw/hylia) starter kit. The site is deployed on Netlify and includes Netlify CMS for content management.

**Purpose**: A scratchpad for Excel, accounting, AI/LLM topics, and other technical notes.

**Live URL**: https://ykcpa.com

## Tech Stack

| Component | Technology |
|-----------|------------|
| Static Site Generator | Eleventy 0.10.0 |
| Templating | Nunjucks (.njk) |
| Styling | Sass (SCSS) with Stalfos framework |
| CMS | Netlify CMS |
| Hosting | Netlify |
| Build Tool | Rollup (for CMS bundling) |

## Directory Structure

```
ykcpa.com/
├── .eleventy.js          # Eleventy configuration
├── netlify.toml          # Netlify build settings
├── package.json          # Dependencies and scripts
├── rollup.config.js      # Rollup bundler config
├── src/
│   ├── _data/            # Global data files (JSON/JS)
│   │   ├── site.json     # Site metadata (name, URL, author)
│   │   ├── navigation.json # Navigation menu items
│   │   ├── tokens.json   # Design tokens (colors, fonts, sizes)
│   │   ├── global.js     # Global helpers
│   │   └── helpers.js    # Template helper functions
│   ├── _includes/
│   │   ├── layouts/      # Page layouts (base, home, post, page)
│   │   ├── partials/     # Reusable components
│   │   ├── macros/       # Nunjucks macros
│   │   ├── icons/        # SVG icons
│   │   └── assets/css/   # Generated CSS (do not edit directly)
│   ├── admin/            # Netlify CMS configuration
│   │   └── config.yml    # CMS field definitions
│   ├── posts/            # Blog posts (Markdown)
│   │   └── posts.json    # Post collection config
│   ├── pages/            # Static pages (Markdown)
│   ├── scss/             # Sass source files
│   │   ├── _config.scss  # Main Sass configuration
│   │   ├── _tokens.scss  # Generated from tokens.json
│   │   ├── _theme.scss   # Theme variables
│   │   └── components/   # Component-specific styles
│   ├── filters/          # Eleventy filters (date, markdown)
│   ├── transforms/       # HTML transforms (minification, parsing)
│   ├── fonts/            # Web fonts
│   ├── images/           # Static images
│   ├── js/               # Client-side JavaScript
│   └── index.md          # Homepage content
├── archive/              # Archived/sample posts (not published)
└── dist/                 # Build output (generated, gitignored)
```

## Development Commands

```bash
# Install dependencies
npm install

# Start development server (watches files, serves at localhost:8080)
npm start

# Build for production
npm run production

# Compile Sass only
npm run sass:process

# Regenerate design tokens for Sass
npm run sass:tokens
```

## Key Files to Know

### Content Management

| File | Purpose |
|------|---------|
| `src/posts/*.md` | Blog posts - Markdown with YAML frontmatter |
| `src/pages/*.md` | Static pages (contact, thank-you, etc.) |
| `src/index.md` | Homepage content |
| `src/_data/site.json` | Site name, URL, author info |
| `src/_data/navigation.json` | Navigation menu links |

### Styling & Theming

| File | Purpose |
|------|---------|
| `src/_data/tokens.json` | Design tokens (colors, fonts, sizes) |
| `src/scss/_config.scss` | Sass configuration and utility generation |
| `src/scss/global.scss` | Main stylesheet entry point |

### Configuration

| File | Purpose |
|------|---------|
| `.eleventy.js` | Eleventy config (filters, collections, plugins) |
| `src/admin/config.yml` | Netlify CMS content types and fields |
| `netlify.toml` | Netlify build command and publish directory |

## Creating Content

### New Blog Post

Create a new Markdown file in `src/posts/` with this frontmatter:

```markdown
---
title: Your Post Title
date: '2025-01-15'
tags:
  - Excel
  - accounting
---

Your post content here...
```

**Notes:**
- Posts automatically use `layouts/post.njk` via `src/posts/posts.json`
- Future-dated posts won't appear until that date
- Add `draft: true` to hide a post

### Frontmatter Fields

| Field | Required | Description |
|-------|----------|-------------|
| `title` | Yes | Post/page title |
| `date` | Yes (posts) | Publish date (YYYY-MM-DD format) |
| `tags` | No | Array of tag names |
| `metaTitle` | No | SEO title override |
| `metaDesc` | No | SEO description |
| `socialImage` | No | Social media share image path |
| `draft` | No | Set to `true` to hide post |

## Theming

Design tokens in `src/_data/tokens.json` control the visual theme:

```json
{
  "colors": {
    "primary": "#34d399",      // Main brand color (green)
    "primary-shade": "#10b981", // Darker variant
    "primary-glare": "#d1fae5", // Lighter variant
    "highlight": "#fef9c3",     // Accent/highlight
    "light": "#ffffff",
    "mid": "#f3f4f6",
    "dark": "#374151",
    "slate": "#6b7280"
  }
}
```

After editing tokens, run `npm run sass:tokens` to regenerate `_tokens.scss`.

## Eleventy Concepts

### Collections

- `posts` - All published blog posts (reverse chronological)
- `postFeed` - Posts for homepage (limited by `maxPostsPerPage`)

### Filters

| Filter | Usage | Description |
|--------|-------|-------------|
| `dateFilter` | `{{ date \| dateFilter }}` | Human-readable date |
| `w3DateFilter` | `{{ date \| w3DateFilter }}` | ISO 8601 date format |
| `markdownFilter` | `{{ content \| markdownFilter }}` | Render Markdown |

### Layouts

| Layout | Used For |
|--------|----------|
| `base.njk` | Base HTML structure |
| `home.njk` | Homepage |
| `post.njk` | Blog posts |
| `page.njk` | Generic pages |
| `archive.njk` | Post archive listing |

## CSS Utility Classes

The Stalfos framework generates utility classes with `sf-` prefix:

```html
<!-- Examples -->
<div class="sf-flow">           <!-- Vertical spacing -->
<span class="text-500">         <!-- Font size scale -->
<p class="leading-loose">       <!-- Line height -->
<div class="pad-top-900">       <!-- Padding -->
<div class="box-flex align-center"> <!-- Flexbox -->
```

## Common Tasks

### Add a Navigation Link

Edit `src/_data/navigation.json`:

```json
{
  "items": [
    {"text": "Home", "url": "/", "external": false},
    {"text": "New Link", "url": "/new-page/", "external": false}
  ]
}
```

### Modify Site Metadata

Edit `src/_data/site.json`:

```json
{
  "name": "ykcpa.com",
  "url": "https://ykcpa.com",
  "authorName": "Josh Krupnick",
  "maxPostsPerPage": 3
}
```

### Add a New Page

1. Create `src/pages/new-page.md`
2. Add frontmatter:

```markdown
---
layout: layouts/page.njk
title: New Page Title
permalink: /new-page/index.html
---
```

## Deployment

The site auto-deploys to Netlify on push to `master` branch:

1. Netlify runs `npm run production`
2. Builds to `dist/` directory
3. Deploys static files

## Netlify CMS

Access the CMS at `/admin` on the live site. Requires Netlify Identity authentication.

**CMS-editable content:**
- Homepage
- Blog posts
- Generic pages
- Site settings (name, URL, author)
- Navigation
- Theme tokens

## Code Conventions

1. **Markdown files**: Use standard Markdown with YAML frontmatter
2. **Nunjucks templates**: 2-space indentation, use partials for reusability
3. **Sass/SCSS**: Follow Stalfos patterns, use design tokens via functions
4. **JavaScript**: ES modules, minimal client-side JS

## Important Notes

- The `dist/` folder is gitignored - never commit build output
- CSS is inlined in the base template for performance
- Service worker caches pages for offline reading
- Third-party comments are disabled by default (`enableThirdPartyComments: false`)

## Repository

- **Source**: https://github.com/yehoshuk/ykcpa.com
- **Based on**: [Hylia Starter Kit](https://github.com/hankchizljaw/hylia)
