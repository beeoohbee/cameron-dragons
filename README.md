# Cameron Dragons

A Jekyll site for Cameron Dragons: a black & gold home page linking out to a themed mini-site for each booster organization, plus a general About page for the umbrella site itself.

## Structure

```
_config.yml                   site settings, nav menu, sub-site collections + defaults
Gemfile                       Ruby dependencies (Jekyll + plugins)
index.md                      home page — grid of links to each sub-site
about.md                      general Cameron Dragons about page
_layouts/
  default.html                 shared header/footer wrapper for main-site pages
  subsite.html                 wrapper for booster-club sub-site pages (own nav, own theme)
  subsite-post.html            wrapper for booster-club news posts
_includes/
  head.html                    shared <head>, pulls in any page.extra_css
  footer.html                  shared footer
_data/subsites.yml             list of booster clubs (name, tagline, url) — drives the home page grid
assets/css/style.css           base styles — black & gold, layout/colors as CSS variables
assets/css/subsites/*.css      per-sub-site color tweaks, layered on top of the base theme

sports-boosters/               Cameron Sports Boosters Association pages (about/contact/news/gallery)
band-boosters/                 Cameron Band Boosters pages (about/contact/news/gallery)
_sports_boosters_posts/        Sports Boosters news posts
_band_boosters_posts/          Band Boosters news posts
```

### Adding a new booster-club sub-site

1. Add an entry to `_data/subsites.yml` (key, name, short_name, tagline, url) — it appears on the home page grid automatically.
2. Add a collection and two `defaults` blocks to `_config.yml` (copy the `sports_boosters_posts` ones and rename).
3. Add a directory of pages, e.g. `orchestra-boosters/index.md`, `about.md`, `contact.md`, `news.md`, `gallery.md` — copy an existing sub-site's pages and edit the copy.
4. Add `assets/css/subsites/<key>.css` with any color overrides for that org (it inherits the black & gold base theme by default even with an empty file).

## Run it locally

1. Install Ruby (if you don't have it): https://www.ruby-lang.org/en/documentation/installation/
2. From this folder, install dependencies:
   ```
   bundle install
   ```
3. Start the local preview server:
   ```
   bundle exec jekyll serve
   ```
4. Open http://localhost:4000 in your browser. Changes to files auto-rebuild.

## Add a new news post

Each sub-site has its own posts folder, e.g. `_sports_boosters_posts/YYYY-MM-DD-your-title.md` or `_band_boosters_posts/YYYY-MM-DD-your-title.md`:

```
---
title: "Your Title Here"
---

Your content here, in Markdown.
```

Layout and theme are applied automatically (see the `defaults` in `_config.yml`), so front matter only needs a `title`.

It will automatically show up on that section's News page (and its home page's "Latest news"), newest first.

## Deploy for free

**Option A — GitHub Pages**
1. Push this folder to a GitHub repository.
2. In the repo Settings → Pages, set the source to your main branch.
3. GitHub builds and hosts it automatically at `https://yourusername.github.io/reponame`.

**Option B — Netlify**
1. Push this folder to a GitHub repository (or drag-and-drop the built `_site` folder onto Netlify).
2. Connect the repo in Netlify; build command `bundle exec jekyll build`, publish directory `_site`.
3. Netlify builds and hosts it, with a free `.netlify.app` URL (or your own domain).
