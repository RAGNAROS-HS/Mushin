# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
# Local dev server (includes drafts)
hugo server -D

# Production build (output → public/)
hugo --minify

# Create new content
hugo new content/devlog/my-post.md
hugo new content/projects/my-project.md
```

Hugo version pinned at **0.156.0 extended** (see `.github/workflows/deploy.yml`).

## Deployment

Pushes to `main` trigger a GitHub Actions workflow that builds with Hugo and deploys `public/` via SFTP to a CloudPanel VPS. Secrets (`SFTP_HOST`, `SFTP_USERNAME`, `SFTP_PASSWORD`, `SFTP_DESTINATION`) are stored in GitHub. The `public/` directory is committed to the repo as well.

## Architecture

Hugo static site using the **FixIt** theme (git submodule at `themes/FixIt`). Two other theme submodules exist (`LoveIt`, `PaperMod`) but are inactive.

**Theme customization** lives entirely in `layouts/partials/custom/`:
- `widgets.html` — injected as the profile partial via `params.customPartials.profile` in `hugo.toml`; renders two side-by-side widgets
- `currently-processing.html` — "Currently Processing" card (reading / listening / training); update this manually when the content changes
- `neural-network.html` — animated neural network widget
- `github-calendar.html` — GitHub contribution calendar

**Content sections**: `content/projects/`, `content/devlog/`, `content/about/` — all standard Hugo markdown with frontmatter.

**Assets / static**: custom CSS/JS go in `assets/` or `static/`; the avatar is at `static/img/stumlogoLookingLeft.png`.

## Key config

`hugo.toml` controls menus, social links, theme params, and the custom partial injection. The `[params.customPartials]` table is the hook that loads `widgets.html` into the home profile area.
