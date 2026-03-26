# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**bigmola.studio** is a Hugo static site deployed to GitHub Pages at `https://bigmola.studio/`. It uses the [Blowfish theme](https://blowfish.page) (installed as a Hugo module) and Dart Sass for styling.

## Commands

```bash
# Local development server
hugo server

# Build site to public/
hugo build --gc --minify
```

## Architecture

- **Content** lives in `content/` as Markdown files
- **Theme** is [Blowfish v2](https://blowfish.page) managed as a Hugo module (`github.com/nunocoracao/blowfish/v2`) — run `hugo mod download` after cloning
- **Overrides** go in `layouts/` (templates) and `assets/` (CSS/JS) — files here take precedence over theme defaults
- **Static files** (images, fonts, etc.) go in `static/`
- **Hugo config** is `hugo.toml` — base URL is `https://bigmola.studio/`, locale is `en-gb`

The CI workflow (`.github/workflows/hugo.yaml`) builds with `--gc --minify` and deploys to GitHub Pages on every push to `main`.

## Hugo-Specific Notes

- Extended Hugo is required (for Dart Sass support)
- The `public/` directory is build output — don't edit it directly
- To add a new content section, create a directory under `content/` and add an `_index.md`
- Custom shortcodes go in `layouts/shortcodes/`
- Blowfish theme config and shortcode docs are at https://blowfish.page/docs/
