# CLAUDE.md - AI Assistant Guide for ykcpa.com

## Project Overview

This is **ykcpa.com**, a personal blog/notes site built with [Astro](https://astro.build/) using the [Brutal](https://github.com/eliancodes/brutal) neobrutalist theme. The site is deployed on Netlify.

**Purpose**: A scratchpad for Excel, accounting, AI/LLM topics, and other technical notes.

**Live URL**: https://ykcpa.com

## Quick Reference

| Task | Command/Location |
|------|------------------|
| Start dev server | `npm run dev` (localhost:4321) |
| Build for prod | `npm run build` |
| New blog post | Create `.md` in `src/data/blog/` |
| Blog ideas | `.claude/ideas.md` |
| Topic context | `.claude/context/*.md` |

## Tech Stack

| Component | Technology |
|-----------|------------|
| Static Site Generator | Astro 5.x |
| Theme | Brutal (neobrutalist) |
| Styling | UnoCSS (Tailwind-compatible) |
| Hosting | Netlify |
| TypeScript | Yes |

## Claude Code Resources

### `.claude/` Directory

```
.claude/
├── ideas.md              # Blog post ideas backlog
└── context/              # Topic-specific writing guides
    ├── excel.md          # Excel post guidelines
    ├── sage-intacct.md   # Sage Intacct post guidelines
    ├── quickbooks.md     # QuickBooks post guidelines
    └── ai-llm.md         # AI/LLM post guidelines
```

**When writing a new blog post:**
1. Check `.claude/ideas.md` for the topic backlog
2. Read the relevant `.claude/context/*.md` file for writing guidelines
3. Create the post in `src/data/blog/`
4. Update `.claude/ideas.md` to track progress

## Directory Structure

```
ykcpa.com/
├── .claude/              # Claude Code resources
│   ├── ideas.md          # Blog post ideas tracker
│   └── context/          # Topic context files
├── astro.config.ts       # Astro configuration
├── uno.config.ts         # UnoCSS configuration
├── tsconfig.json         # TypeScript config
├── netlify.toml          # Netlify build settings
├── package.json          # Dependencies and scripts
├── public/               # Static assets (favicon, etc.)
├── src/
│   ├── assets/           # Images processed by Astro
│   ├── components/
│   │   ├── blog/         # Blog-specific components
│   │   ├── generic/      # Reusable components
│   │   ├── home/         # Homepage components
│   │   ├── layout/       # Header, footer, navigation
│   │   └── errors/       # Error page components
│   ├── content.config.ts # Content collection schema
│   ├── data/
│   │   └── blog/         # Blog posts (Markdown)
│   ├── layouts/          # Page layouts
│   ├── pages/            # Route pages (.astro)
│   │   ├── index.astro   # Homepage
│   │   ├── contact.astro # Contact page
│   │   ├── blog/         # Blog routes
│   │   └── feed.xml.js   # RSS feed
│   └── styles/           # Global CSS
└── dist/                 # Build output (gitignored)
```

## Development Commands

```bash
# Install dependencies
npm install

# Start development server (localhost:4321)
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Key Files to Know

### Content Management

| File | Purpose |
|------|---------|
| `src/data/blog/*.md` | Blog posts - Markdown with YAML frontmatter |
| `src/pages/index.astro` | Homepage |
| `src/pages/contact.astro` | Contact form (Netlify Forms) |
| `src/content.config.ts` | Blog post schema definition |

### Configuration

| File | Purpose |
|------|---------|
| `astro.config.ts` | Astro config (site URL, integrations) |
| `uno.config.ts` | UnoCSS/Tailwind utilities |
| `netlify.toml` | Netlify build command |

### Layout & Components

| File | Purpose |
|------|---------|
| `src/layouts/Default.astro` | Base page layout |
| `src/layouts/BlogPost.astro` | Blog post layout |
| `src/components/layout/BaseNavigation.astro` | Site navigation |
| `src/components/layout/BaseFooter.astro` | Site footer |

## Creating Content

### New Blog Post

Create a new Markdown file in `src/data/blog/` with this frontmatter:

```markdown
---
title: Your Post Title
pubDate: 03/20/2026
author: "Josh Krupnick"
tags:
  - Excel
  - accounting
description: A brief description for previews and SEO.
---

Your post content here...
```

**Notes:**
- `pubDate` format: MM/DD/YYYY
- `imgUrl` is optional (for featured images)
- Add `draft: true` to hide a post

### Frontmatter Fields

| Field | Required | Description |
|-------|----------|-------------|
| `title` | Yes | Post title |
| `pubDate` | Yes | Publish date (MM/DD/YYYY) |
| `author` | Yes | Author name |
| `tags` | Yes | Array of tag names |
| `description` | Yes | SEO/preview description |
| `imgUrl` | No | Featured image path |
| `draft` | No | Set to `true` to hide post |

### Common Tags

Use consistent tags across posts:
- `Excel`, `formulas`, `productivity`
- `Sage Intacct`, `ERP`
- `QuickBooks`, `QBO`, `bookkeeping`
- `AI`, `LLM`, `automation`
- `accounting`, `small business`

## Styling

Uses UnoCSS with Tailwind-compatible utility classes. The theme provides:

- `poppins` - Body text font
- `outfit` - Display font
- `dm-serif` - Serif headings
- `righteous` - Logo/brand font
- `card-shadow` - Neobrutalist box shadow

Colors: `bg-pink`, `bg-green`, `bg-blue`, `text-white`, etc.

## Deployment

Auto-deploys to Netlify on push to `master`:

1. Netlify runs `npm run build`
2. Builds to `dist/` directory
3. Deploys static files

## Contact Form

The contact page uses Netlify Forms with honeypot spam protection. Form submissions go to the Netlify dashboard.

## Code Conventions

1. **Blog posts**: Markdown with YAML frontmatter in `src/data/blog/`
2. **Components**: Astro components (.astro) with TypeScript frontmatter
3. **Styling**: UnoCSS utility classes (Tailwind-compatible)
4. **Pages**: File-based routing in `src/pages/`

## Workflow Tips

### Writing a New Post
1. Pick a topic from `.claude/ideas.md`
2. Review context in `.claude/context/[topic].md`
3. Create `src/data/blog/your-post-slug.md`
4. Run `npm run dev` to preview
5. Update `.claude/ideas.md` (move to Published)

### Adding Images
1. Save images to `src/assets/`
2. Reference in markdown: `![alt text](../../assets/image.png)`
3. Astro will optimize automatically

### Testing Changes
```bash
npm run build && npm run preview
```

## Repository

- **Source**: https://github.com/yehoshuk/ykcpa.com
- **Theme**: [Brutal](https://github.com/eliancodes/brutal) by ElianCodes
