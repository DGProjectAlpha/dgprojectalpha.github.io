# dgprojectalpha.github.io — CLAUDE.md

## Project Overview

GitHub Pages static site for DGProjectAlpha, serving as the public-facing landing page and support hub for the **UltraCalendar** Android app (available on Google Play). The site lives at `dgprojectalpha.dev` (custom domain via CNAME).

The site hosts:
- UltraCalendar app landing page with feature list, changelog, and Play Store badge
- Privacy policy and terms of service (plain text)
- Google Site Verification file

## CLAUDE.md Maintenance Rule
**Update this file whenever:** new pages added, site structure changes, or significant content/functionality added that isn't documented here. This file is the source of truth for any agent working on this project.
- AdMob / Google advertising verification (`app-ads.txt`)

## Directory Structure

```
dgprojectalpha.github.io/
├── index.html           # Main landing page (UltraCalendar app page + changelog)
├── privacypolicy.txt    # Privacy policy (plain text)
├── termsofservice.txt   # Terms of service (plain text)
├── app-ads.txt          # Google AdMob/advertising verification
├── googleed679dcce589999e.html  # Google Search Console verification
└── CNAME                # Custom domain: dgprojectalpha.dev
```

## Key Files

| File | Purpose |
|------|---------|
| `index.html` | Single-page site: header, about, features, data usage, changelog, legal links, contact, footer. All CSS is inline (`<style>` block). No JS. |
| `privacypolicy.txt` | Plain text privacy policy linked from the app store listing and the site |
| `termsofservice.txt` | Plain text terms of service |
| `app-ads.txt` | AdMob app-ads.txt for advertising inventory verification |
| `CNAME` | Contains `dgprojectalpha.dev` — tells GitHub Pages to serve on this domain |

## Tech Stack / Dependencies

- **Pure static HTML/CSS** — no JavaScript, no build tools, no dependencies, no frameworks
- **Hosting**: GitHub Pages (auto-deployed from `main` branch push)
- **Custom domain**: `dgprojectalpha.dev` (DNS → GitHub Pages servers)
- **No build step** — edit files and push; GitHub Pages serves directly

## Build / Run Commands

No build required. To preview locally:

```bash
# Any static file server works
python3 -m http.server 8080
# Then open http://localhost:8080
```

To deploy: push to `main` branch on GitHub. GitHub Pages auto-deploys within ~1 minute.

## Architecture Notes

- Single `index.html` with all CSS inlined — no external stylesheets, no JS, no CDN dependencies
- Changelog is maintained manually inside `index.html` as a series of `.changelog-entry` divs, newest version first
- Play Store badge links directly to `https://play.google.com/store/apps/details?id=com.dgprojectalpha.ultracalendar`
- Contact email: `dgprojectalpha@gmail.com`
- All data stays local on device (no server-side component); privacy policy reflects this

## App Context (UltraCalendar)

UltraCalendar is a Material 3 Android calendar app. Current version: **v1.6** (as of changelog). Key features referenced on the site:
- Google Calendar, Tasks, and Contacts sync
- Routines with streak tracking (v1.6)
- 6 widget styles: Dynamic, Simple, Month, Flip, Routine Banner, Routine Square
- Weather via Open-Meteo
- Premium tier ($0.99): custom colors, widget transparency, routine heatmap, ad-free
- Monetization: AdMob banner/native ads, in-app purchase for premium
- Firebase: FCM push notifications, Analytics

## Gotchas and Quirks

- **Changelog is in `index.html`** — there is no CMS or separate data file. Add new entries manually as `.changelog-entry` divs at the top of the Changelog `<section>`.
- **Version dates use DD/MM/YYYY format** in the changelog (e.g., `09/04/2026`).
- **`app-ads.txt`** must stay at the root and match AdMob publisher ID exactly — do not rename or move it.
- **`googleed679dcce589999e.html`** is a Google Search Console verification file — do not delete it.
- **No HTTPS config needed** — GitHub Pages handles TLS for custom domains automatically.
- **Privacy policy is plain text**, not HTML — this is intentional for easy app store linking and parsing.
