# Copilot Instructions

## Project Overview

Personal blog and portfolio site for Alperen Aksoy, built with Hugo and the PaperMod theme. Deployed to GitHub Pages via GitHub Actions.

## Commands

```bash
# Local development server (with drafts)
hugo server --buildDrafts

# Production build
hugo --gc --minify

# Create a new blog post
hugo new content blog/my-post-title.md
```

## Architecture

- **Static site generator:** Hugo (extended edition)
- **Theme:** PaperMod, installed as a Git submodule at `themes/PaperMod` — do not modify theme files directly; use Hugo's override mechanism by placing files in the project's `layouts/` or `assets/` directories
- **Config:** `hugo.yaml` (single file, not split config)
- **Deployment:** Push to `main` triggers `.github/workflows/hugo.yml` → builds with Hugo → deploys to GitHub Pages

## Content Structure

- `content/blog/` — Blog posts (Markdown with YAML front matter)
- `content/about.md` — About page
- `content/contact.md` — Contact page
- `content/projects.md` — Projects showcase (single page, not a list/section)
- `content/search.md` — PaperMod search page (special layout, do not change `layout: search`)

## Conventions

- **Taxonomy:** Tags only (no categories). Add tags in front matter as `tags: ["tech", "AI"]`
- **Front matter format:** YAML (delimited by `---`)
- **Post filenames:** Kebab-case (`my-post-title.md`)
- **Drafts:** Set `draft: true` in front matter; drafts are excluded from production builds
- **Theme customization:** Override PaperMod templates by copying them to the project's `layouts/` directory — never edit files inside `themes/PaperMod/`
- **Images:** Place in `static/images/` and reference as `/images/filename.png`
- **Config format:** YAML (`hugo.yaml`) — keep it as a single file
