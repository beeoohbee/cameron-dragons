# Cameron Dragons

The source for **[camerondragons.com](https://camerondragons.com)**: a community hub that links to the booster clubs, sports teams, and youth programs supporting Cameron's young people. Some organizations get their own themed mini-site here (the "sub-sites"); others are linked out to their own website or Facebook page.

It's a [Jekyll](https://jekyllrb.com) static site styled after the Cameron R-I School District's gold and black, and it's published automatically by GitHub Pages whenever changes are pushed to `main`.

## What's on the site

**Main site**
- **Home** (`index.md`) — a landing hero (image on the left fading into black, welcome text and a button on the right), then a card for every organization, then a "Don't see your organization?" note linking to Contact.
- **About** (`about.md`) — what the site is for and the site's mission statement.
- **Contact** (`contact.md`) — the site email (mocamerondragons@gmail.com) and a contact form handled by [Formspree](https://formspree.io), which emails submissions to that address. A hidden honeypot field filters out bots. Manage the form and spam settings in the Formspree dashboard. Linked from the top menu and every page's footer.

**Cameron Sports Boosters Association** (`sports-boosters/`)
- **Home** — the club logo, the "Join today!" section with the membership QR code and form link, and the "One Cameron" band.
- **About** — the club's mission and officer cards.
- **Members** — members grouped by tier (Gold Business, Silver Family, Bronze Individual, Coaches & Families).
- **Join** — membership levels and prices, the sign-up form (with QR code), ways to pay, and a Donate (Venmo) button.
- **Activity** — what the club has funded (photo cards) and scholarship requirements.
- **Contact** — club email and Facebook.
- News is built but hidden for now (see `sports-boosters/news.md`).

**Cameron Band Boosters** (`band-boosters/`) — placeholder pages, **not published** (listed under `exclude:` in `_config.yml`); the home page card points to the band's Facebook page instead.

**404 page** (`404.html`) — shown for any address that doesn't exist.

## Common edits

| To change… | Edit |
|---|---|
| The organization cards on the home page (add, rename, reorder, link) | `_data/subsites.yml` |
| Home page hero text, button, or image | front matter at the top of `index.md` |
| Sports Boosters officers | `_data/officers/sports-boosters.yml` |
| Sports Boosters members | `_data/members/sports-boosters.yml` (**names only** — see below) |
| Activity cards and photos | front matter at the top of `sports-boosters/activity.md` |
| Sports Boosters email | `sports-boosters/contact.md` |
| Sports Boosters Facebook link / social icons | `social:` on the `sports-boosters` entry in `_data/subsites.yml` |
| Membership form link, Venmo handle | `join_form:` / `venmo:` on the `sports-boosters` entry in `_data/subsites.yml` (regenerate `assets/images/sports-boosters/join-qr.png` if the form changes) |
| Membership levels and prices | front matter at the top of `sports-boosters/join.md` |
| Colors and fonts | the variables at the top of `assets/css/style.css` |
| Site address, description, top menu | `_config.yml` |

### Organization cards (`_data/subsites.yml`)

Each entry is one card on the home page. There are three kinds:

- **Sub-site** — has `url: /its-folder/`; the card says "Learn more →" and links to the mini-site.
- **Outside link** — `external: true` plus `url:` (or `external_url:`) and `external_label:` (e.g. `Facebook`, `Website`); the card opens that page in a new tab.
- **Coming soon** — `coming_soon: true`; a gray, non-clickable placeholder card.

### Members list — privacy

The repository is public, so `_data/members/sports-boosters.yml` holds **member names only**. Never add addresses, emails, phone numbers, payment notes, or student athletes' names; student-athlete memberships are shown as a count (`student_athlete_count`).

### Photos

- Put images under `assets/images/` (sub-site images in `assets/images/<sub-site>/`). Resize large photos first — about 800px wide is plenty for cards.
- Stock photos on the Activity page come from Wikimedia Commons and carry `credit`, `credit_url`, `license`, and `license_url` fields; most licenses require that credit stay with the photo. When you replace one with your own photo, remove those fields.
- The home hero currently uses small placeholder art (`assets/images/hero-placeholder.jpg`). For a real photo, set `image:` in `index.md` and change `image_fit` to `cover`.

### Icons

[Font Awesome Free](https://fontawesome.com/icons) is loaded on every page, so any free icon can be used, e.g. `<i class="fa-solid fa-trophy" aria-hidden="true"></i>` or `<i class="fa-brands fa-instagram" aria-hidden="true"></i>`.

### Favicon and link previews

- Browser icons (`favicon.ico`, `apple-touch-icon.png`, `assets/images/icons/`) are cropped from the home hero art.
- `assets/images/og-image.jpg` (1200×630) is the preview image shown when the site is shared on Facebook, in texts, etc. A page can use a different one with `share_image:` in its front matter, and its own preview text with `description:`.

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
4. Open http://localhost:4000 in your browser. Changes to files rebuild automatically (changes to `_config.yml` need a restart).

If pages were renamed or removed, run `bundle exec jekyll clean` first so old copies don't linger.

**Dropbox note:** this folder lives in Dropbox, which can sync stale copies back into the generated `_site/` folder and make local previews look out of date. If a preview looks wrong, build somewhere outside Dropbox (`bundle exec jekyll serve -d /tmp/cameron-site`). The live site isn't affected — GitHub builds it from scratch.

## Publishing

The site deploys itself: every push to `main` runs the **Deploy site to GitHub Pages** workflow (`.github/workflows/pages.yml`), which builds the site with the exact gems in `Gemfile.lock` and publishes it. Watch progress under the repo's **Actions** tab; a green check means it's live.

One-time setup, in the repo's **Settings → Pages**:
- **Source:** GitHub Actions
- **Custom domain:** `camerondragons.com` (also stored in the `CNAME` file), with **Enforce HTTPS** checked
- `url:` in `_config.yml` must match (`https://camerondragons.com`) so the sitemap and link previews use full addresses

## Adding a new sub-site

1. Add an entry to `_data/subsites.yml` (`key`, `name`, `short_name`, `tagline`, `url: /<key>/`).
2. In `_config.yml`, add a news collection and two `defaults` blocks — copy the `sports_boosters_posts` ones and rename.
3. Add a folder of pages (`<key>/index.md`, `about.md`, `contact.md`, …) — copy an existing sub-site's pages and edit the copies.
4. Add `assets/css/subsites/<key>.css` (it can stay empty; the shared theme applies).
5. Optional: `_data/officers/<key>.yml` and `_data/members/<key>.yml` for officer cards and a Members page (the Members menu link appears automatically).

## Adding a news post

Create `_<sub_site>_posts/YYYY-MM-DD-your-title.md`, e.g. `_band_boosters_posts/2026-10-01-fall-concert.md`:

```
---
title: "Your Title Here"
---

Your content here, in Markdown.
```

It appears on that sub-site's News page, newest first. (Sports Boosters news is currently hidden — to turn it back on, delete `published: false` in `sports-boosters/news.md` and set the collection's `output` back to `true` in `_config.yml`.)
