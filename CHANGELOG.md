# Drinks By Neat — Site v2 — Build Changelog

Built: 2026-05-27
Location: `/Users/andreassanidiotis/Desktop/Drinks By Neat/site-v2/`

## What's in this folder

```
site-v2/
├── index.html                    # Home
├── work/index.html               # Work — 4 case studies
├── services/index.html           # Services — 5 packages
├── blog/index.html               # Notes — index page
│   ├── japanese-hard-shake/index.html
│   ├── japanese-stirring/index.html
│   └── sugar/index.html
├── about/index.html              # About — Andreas's story
├── contact/index.html            # Contact
├── css/style.css                 # Single design-system stylesheet
└── CHANGELOG.md                  # This file
```

## How to deploy

The new site is structured to slot into your existing GitHub repo with **zero URL breakage**.

1. In your repo, replace these files with the matching files from this folder: `index.html`, `services/index.html`, `about/index.html`, `blog/index.html`, `contact/index.html`.
2. Add the new files: `work/index.html`, `css/style.css`, and the three new blog post folders (`blog/japanese-hard-shake/`, `blog/japanese-stirring/`, `blog/sugar/`).
3. **Delete** `ai-services/` from the repo — that page is gone per positioning decision.
4. Keep these existing assets untouched: `assets/images/logo.png`, `assets/images/favicon.ico`, and the four existing blog post folders (Milk Wash, Mango Sticky Rice, Brown Butter, Enzymes) with their images.
5. Commit on a feature branch, preview on GitHub Pages, push to main when happy.

## What changed vs. the old site

**Visible to visitors:**
- Hero copy rewritten — credentials-led, not jargon-led. World's 50 Best #25, two-time Tales nominee, Spirited Awards Regional Top 10 Honoree front and center.
- "AI Services" page removed entirely. AI work is held back for scoping calls.
- New `/work/` page with four case studies: Lost & Found Drinkery, Tocayo, In Plain Sight, Casa de Cuba.
- New `/services/` page with five priced packages (Opening, Refresh, Prep-Lab, White-Label/RTD, Advisory Retainer) — published prices, not "contact for quote."
- Blog renamed to "Notes" in the nav (URL stays `/blog/` for SEO preservation).
- About page rewritten as a story, not a vendor pitch.
- Design system: Fraunces serif + Inter sans on a warm cream background, oxblood accent. Editorial restraint over salesy energy.
- Mobile-first nav, sticky header, proper typography scale.
- Three new long-form posts migrated from Notion: Japanese Hard Shake, Japanese Stirring, Sugar.

**Under the hood:**
- One CSS file (`/css/style.css`) handles every page. No frameworks, no build step.
- Google Fonts loaded via CDN (Fraunces + Inter).
- Vanilla JS for mobile nav toggle and sticky-header scroll state.
- All internal links use root-relative paths (`/work/`, `/blog/japanese-hard-shake/`) so the site works at any deploy root.

## Still to do — v1.5

These are the things that would push the site from "much better than what's there" to actually award-worthy:

1. **Photography.** The single biggest lift. The current site relies on typography; real photography of the bars (Lost & Found, Tocayo, In Plain Sight), the prep lab, the rotovap, finished drinks, and Andreas at work would transform it. Until photos are ready, the typography-led design carries the page.

2. **The remaining 4 blog posts from Notion need migration:**
   - Yuzu Kosho Margarita (recipe long-form)
   - Rotary Evaporator (technical guide — strongest credibility piece)
   - Shiitake Butter Washed Old Fashioned (fat washing) — note: overlaps with existing "Brown Butter in Cocktails" post; check before publishing
   - Sous Vide Mixology Parts 1 & 2 (two-part series)

3. **Calendly link** in the Contact page is a placeholder URL. Set up your real booking link and swap.

4. **Email address.** Contact page uses `andreas@drinksbyneat.com` — confirm this routes correctly.

5. **OG image.** The `/assets/images/og-image.jpg` referenced for social sharing doesn't exist yet. Once photography is in, generate a 1200×630 OG image.

6. **Footer pull quote.** Currently placeholder. Worth sourcing a real quote from a former operator (chef-partner at Lost & Found, GM at Tocayo) for the About page recognition section.

7. **Privacy Policy.** Old policy still at `/privacy-policy.html` — review and update.

8. **Drop "Design Your Own Foam"** from any future migrations — the Notion piece appears to be republished ChefSteps content. Either rewrite from scratch or skip.

## Two facts the old dossier was missing

Surfaced during the Notion deep-dive:
- **Casa de Cuba (Abu Dhabi, 2019)** — your UAE consulting credit, now documented in the Work page.
- **Tocayo, Best New Restaurant Cyprus 2021** — a verifiable accolade that strengthens the Tocayo case study.

Both have been added to the Work page and the dossier should be updated to include them as verified credentials.

## Design notes (for future iteration)

- **Type system:** Fraunces (display + body serif, variable font with optical sizing) and Inter (sans). Both free, both load via Google Fonts. Variable font means we can scale headlines up to 144pt without a separate display weight.
- **Color tokens are in `:root` at the top of style.css.** Changing the accent from oxblood to a different color is a one-line edit (`--accent: #...`).
- **Section padding uses CSS `clamp()`** so spacing scales smoothly from mobile to desktop without breakpoints.
- **Reading width** is locked to a 680px max (`--reading-max`) for long-form content. Wider than this is uncomfortable to read; narrower feels cramped.

## QA before push

Recommend testing on:
- Mobile (375px Safari iOS) — header collapse, hero stack, work card single-column
- Tablet (768px–1024px) — mid-breakpoint behavior
- Desktop (1440px+) — full layout
- A long-form article page at desktop width — confirm reading width is comfortable

Print stylesheet not included; add if needed.

---

Ship it.
