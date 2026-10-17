# Cameron Dragons — TODO

The top 10 improvements for camerondragons.com and its sub-sites, most valuable first. Each item says who it's waiting on: **content** (photos, wording, or decisions from the club), **setup** (an account or setting outside this repo), or **code** (can be built in the repo).

_Last reviewed: October 17, 2026._

---

## 1. Replace the home page hero art with a real photo — *content*

The main hero still uses a small (235×215) placeholder of the district's dragon artwork, so it looks soft on large screens, and the district's mascot art may need permission to use.

- [ ] Get a wide, high-resolution photo of Cameron students (at least 1600px wide), with permission to publish it
- [ ] Set `image:` in `index.md` to the new file and change `image_fit: contain` to `cover`
- [ ] Regenerate the favicon, `apple-touch-icon.png`, and the link-preview image (`assets/images/og-image.jpg`) from the new artwork
- [ ] Confirm permission for any district logo/mascot artwork still in use

## 2. Replace the main contact form with a real form service — *setup + code*

`contact.md` opens the visitor's own email app (`mailto:`), which does nothing for people without a mail app set up, and it shows the email address on the page, where spam bots can collect it.

- [x] Create a shared Cameron Dragons email address — **mocamerondragons@gmail.com**, now used on `contact.md`
- [x] Sign up for a free form backend and point the form at it — **Formspree** (`formspree_url` in `contact.md`), with a honeypot field for spam
- [ ] Send a real test message and confirm it arrives (Formspree may ask you to confirm the first submission)
- [ ] Optional: turn on Cloudflare Turnstile or reCAPTCHA in the Formspree dashboard if spam gets through

## 3. Add an events calendar — *setup + code*

Game days, fundraisers, concessions shifts, the Youth Basketball Tournament (February), the Turkey Trot 5K, and the Football Jamboree are the main reasons families would come back to the site.

- [ ] Create a shared Google Calendar for the Sports Boosters (and later other groups)
- [ ] Add an "Events" page to the sub-site that embeds or lists it, and show the next few events on the Sports Boosters home page

## 4. Add a volunteer sign-up page — *content + code*

The membership form already asks members which activities they'll help with, but the site never lists the opportunities.

- [ ] Add a "Volunteer" section (or page) to Sports Boosters listing: Football Jamboree concessions, merchandise sales at home football and basketball games, the Youth Basketball Tournament, team liaisons, and the Turkey Trot 5K committee
- [ ] Link it to a sign-up tool (SignUpGenius or a Google Form) with dates and shifts

## 5. Finish the Activity page — *content*

- [ ] Photos for **Dragon Sign at Football Field** and **Softball and Tennis Parking Lot Paint** (currently "Photo coming soon")
- [ ] Replace the remaining stock photos (batting cages, water cow, cross country tents, track tents, banquet meals, utility vehicle) with the club's own — then remove their `credit` fields. The **water cow** photo shows another school's (Miami) logo and should go first
- [ ] Confirm the titles and captions written for the new cards (Tennis Tent, Sports Boosters Trailer, Dugout Logo, Soccer Goals, Softball Fence Cups) and the **Utility Vehicle** title (all marked "confirm" in `sports-boosters/activity.md`)

## 6. Complete the scholarship details — *content*

The Scholarships panel lists eligibility and says an application is required, but not how to apply.

- [ ] Link the scholarship application (form or PDF)
- [ ] Add the deadline, award amount(s), and who to contact
- [ ] Optionally list past recipients each spring

## 7. Make updates possible without a developer — *setup*

Every change to members, officers, photos, or news currently goes through the code. Board members should be able to make routine updates themselves.

- [ ] Connect a free Git-based editor such as [Pages CMS](https://pagescms.org) to this repo and configure it for `_data/members/`, `_data/officers/`, `_data/subsites.yml`, the Activity cards, and news posts
- [ ] Give the Sports Boosters secretary/social media officer access
- [ ] Keep the "names only" privacy rule for the members list (see README)

## 8. Bring back Sports Boosters news — *content + code*

News is built but hidden (`published: false` in `sports-boosters/news.md`) because there are no real posts yet.

- [ ] Delete the sample post `_sports_boosters_posts/2026-08-20-fall-schedule-posted.md` and write 2–3 real ones (recaps, reminders, thank-yous to sponsors)
- [ ] Remove `published: false` and set `sports_boosters_posts` `output: true` in `_config.yml`
- [ ] Commit to a posting rhythm (even monthly), or cross-post from Facebook/Instagram

## 9. Build out the other organizations — *content*

- [ ] **Band Boosters:** the sub-site is hidden (`exclude:` in `_config.yml`) and still full of placeholders (fake phone/address, "Name" officers, sample post). Gather a mission, officers, contact info, and photos — then publish it, or delete the folder if Facebook will be the band's only home
- [ ] **Ag Boosters** and **Choir Boosters:** still "Coming soon" — find a link (website or Facebook) or a contact for each
- [ ] Replace the placeholder taglines written for the Swim Team, Baseball Association, Youth Football and Cheer, and PTSA cards with each group's own wording
- [ ] Reach out to other Cameron youth groups that might want a card (the "Don't see your organization?" box invites this)

## 10. Search engines (SEO) and measuring use — *setup + content*

The site's own SEO basics are done (see "Done recently"). What's left needs accounts, outreach, or new content:

**Setup (one-time)**
- [ ] In the repo's **Settings → Pages**, confirm **Source** is **GitHub Actions**. The live site appeared to be built by GitHub's older built-in builder, which is why the sitemap, robots.txt, and feed were missing
- [ ] After the next deploy, confirm https://camerondragons.com/sitemap.xml and https://camerondragons.com/robots.txt load
- [ ] Verify `camerondragons.com` in [Google Search Console](https://search.google.com/search-console) (DNS TXT record in GoDaddy) and submit `https://camerondragons.com/sitemap.xml`
- [ ] Do the same in [Bing Webmaster Tools](https://www.bing.com/webmasters) (it can import from Search Console)
- [ ] Check the structured data with Google's [Rich Results Test](https://search.google.com/test/rich-results) on the home page and the Sports Boosters home page
- [ ] Verify `camerondragons.com` as a domain in GitHub account settings (protects against takeover of the custom domain)
- [ ] Add privacy-friendly visitor stats (e.g. GoatCounter or Cloudflare Web Analytics) to see which pages and links people use

**Links from other sites** — the biggest ranking factor for a local site
- [ ] Ask the Cameron R-I School District to link to camerondragons.com (athletics or community page)
- [ ] Ask the Cameron Chamber of Commerce to add camerondragons.com to its organization listings
- [ ] Add the website link to the "About"/bio of each group's Facebook and Instagram profiles
- [ ] Ask Gold sponsors to link to the Sports Boosters page from their websites
- [ ] List the Sports Boosters in local/nonprofit directories (city of Cameron "Clubs & Organizations" page, Google Business Profile if appropriate)

**Content** (see also items 3 and 8)
- [ ] Publish events and news regularly, using the words people search for ("Cameron Turkey Trot 5K", "Cameron youth basketball tournament", "Cameron Dragons football schedule")
- [ ] Give each new page its own `description:` (about 120–160 characters) in its front matter; use `seo_title:` for key pages
- [ ] Create a Sports Boosters–branded link-preview image (club logo) so shared Sports Boosters links show their own branding (`share_image:` front matter)

**Sponsors**
- [ ] Ask sponsors for official logo files (and permission), and add a link for C L Bland Farms if it has a website or Facebook page

---

## Done recently

- HTTPS certificate issued and **Enforce HTTPS** turned on
- Join page with membership levels, ways to pay, and Donate (Venmo) buttons
- Gold sponsor logo strip on the Sports Boosters home page; logos for all nine Gold members
- Contact in the main menu; friendly 404 page; lazy-loaded images
- Activity page filled with the club's own photos; Scholarships moved to the top
- Instagram and Facebook links in the Sports Boosters header, contact page, and home page card
- SEO basics: sitemap, robots.txt, and feed now build on any builder; unique search titles (with "Cameron, MO") and descriptions on every page; structured data describing Cameron Dragons and the Sports Boosters (name, logo, email, social profiles, location); fixed main pages showing the Sports Boosters description to search engines
- Sports Boosters logo converted to WebP (531 KB → 76 KB)
- Contact form now sends via Formspree to mocamerondragons@gmail.com
