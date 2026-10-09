# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A Jekyll static site for "Cameron Dragons": a black & gold home page that links out to a themed mini-site ("sub-site") for each booster organization, plus a general About page for the umbrella site. No JS build step, no CMS, no server-side code.

## Commands

```bash
bundle install              # install Jekyll + plugins (first time / after Gemfile changes)
bundle exec jekyll serve    # run local dev server at http://localhost:4000, auto-rebuilds on change
bundle exec jekyll build    # produce static output in _site/
bundle exec jekyll clean    # remove _site/ and the cache — run before build if pages were renamed/removed,
                             # since `build` doesn't delete stale output on its own
```

There are no tests, linter, or CI config in this repo.

## Architecture

### Main site

- **`_config.yml`** — site title/description, the main `nav:` list (currently just Home/About), the `collections:` and `defaults:` that power each sub-site, and `exclude:` (non-output files like README/CLAUDE.md/Gemfile).
- **`_layouts/default.html`** — the layout for the top-level pages (`index.md`, `about.md`).
- **`_includes/head.html`** / **`_includes/footer.html`** — shared across *both* `default.html` and the sub-site layouts. `head.html` reads a page's `extra_css` front-matter array (if any) and links each file after `style.css` — this is the hook sub-sites use to layer on their per-org customization.
- The main site has its own `contact.md` (a form that opens a `mailto:` to the site owner, linked from the shared footer) but no news/blog collection — news only exists per sub-site.
- `_data/subsites.yml` entries with `coming_soon: true` render as non-clickable placeholder cards on the home page.

### Sub-sites (booster clubs)

- **`_data/subsites.yml`** — the list of booster clubs (`key`, `name`, `short_name`, `tagline`, `url`). The home page grid (`index.md`) loops over this, and `_layouts/subsite.html` looks up the current one by `page.subsite` to build its header/nav. **This is the file to edit to rename a sub-site or change its tagline** — page templates don't hardcode org names.
- **`_layouts/subsite.html`** — standalone layout (does not extend `default.html`) with its own header: a small "← Cameron Dragons" link back to the main site plus the sub-site's own Home/About/Members/News/Gallery-or-Activity/Contact nav (Members only if `_data/members/<key>.yml` exists; Activity replaces Gallery when the sub-site has an `activity.md` page).
- **`_layouts/subsite-post.html`** — extends `subsite.html` via `layout:` front matter, adds the post date and a "back to news" link.
- **Per-sub-site content directories** (`sports-boosters/`, `band-boosters/`) — each holds `index.md`, `about.md` (mission + officers), `contact.md`, `news.md`, and `gallery.md` (Sports Boosters has `activity.md` instead — what the club has funded, plus scholarships). Front matter on these pages is minimal (`title`, `permalink`) because `layout`, `subsite`, `site_name`, and `extra_css` all come from the path-scoped `defaults:` in `_config.yml`.
- **Per-sub-site news collections** (`_sports_boosters_posts/`, `_band_boosters_posts/`) — `YYYY-MM-DD-title.md` convention. Each collection is registered in `_config.yml` with its own permalink and gets its layout/theme via a `defaults:` block scoped by collection `type`, not by path.

**To add a new booster-club sub-site:** add an entry to `_data/subsites.yml`, add a collection + two `defaults` blocks to `_config.yml` (copy an existing pair), add a page directory (copy an existing one), and add a theme override file under `assets/css/subsites/`.

### Theming (black & gold, inherited + customizable)

Colors are CSS custom properties, cascaded across two layers:

1. **`assets/css/style.css`** — the whole site's base theme: structural CSS (layout, header, grid, nav, footer) plus the `:root` color and font variables (`--accent`, `--accent-strong`, `--accent-contrast`, `--ink`, `--text`, `--bg`, `--muted`, `--border`, `--card-bg`, `--font-display`, `--font-body`). These follow the Cameron R-I School District site (cameron.k12.mo.us): gold `#ffc71f` header band, near-black `#010100` footer/ink, white pages, Paytone One + Poppins (loaded from Google Fonts in `head.html`). Gold is only used as a fill/border/underline, never as text on white (unreadable). Every page — main site and sub-sites alike — gets this.
2. **`assets/css/subsites/<key>.css`** — one file per sub-site (`sports-boosters.css`, `band-boosters.css`), currently empty (comment only) so every sub-site matches the district look. This is the sub-site-level customization point — add variable overrides here for per-org tweaks.

Which extra file(s) load on a given page is controlled by that page's `extra_css` front-matter array, set via the `defaults:` blocks in `_config.yml` — not hardcoded in any layout. The main site's pages set no `extra_css`, so they render with the base theme only.
