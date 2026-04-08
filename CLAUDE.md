# Masters Pool 2026

## Project Overview
A golf pool web app for The Masters tournament. Single-page HTML app with Supabase backend, deployed on Vercel.

## Tech Stack
- **Frontend:** Single `index.html` file (vanilla HTML/CSS/JS)
- **Backend:** Supabase (Postgres + Realtime)
- **Hosting:** Netlify (auto-deploys on push to main)
- **Live URL:** https://masters-pool-2026-948.netlify.app/
- **Netlify Dashboard:** https://app.netlify.com/projects/masters-pool-2026-948

## Key Features
- Pool leaderboard with scoring (top 4 of 6 picks count per round)
- 6-tier pick system: Favorites, Contenders, Sleepers, Longshots, Wild Card 1 & 2
- Live ESPN score sync
- Tiebreaker system (winner's score guess)
- Admin panel (password: masters2026)
- Teams hidden until tournament starts (admin toggle: "Reveal Teams")

## Supabase
- **Project ID:** ggclubyvmdfgoeeoiqhi
- **Tables:** `entries`, `settings`
- Client variable is `sb` (not `supabase` - renamed to avoid CDN conflict)

## Admin Settings
- **Lock Entries:** Prevents new signups
- **Reveal Teams:** Shows picks on leaderboard (turn on Thursday when tournament starts)
- **Active Round:** Which round is being scored
- **Tiebreaker:** Score guess / Best single round / None

## Common Tasks

### Add a player to a tier
In the `seed()` function or via Admin > Manage Field

### Change scoring rules
Look for `entRnd()` function - calculates round scores
Look for `gsc()` function - gets golfer score

### Modify leaderboard display
Look for `renderLB()` function

### Update entry form
Look for `renderEnter()` function and `#tab-enter` HTML section

## Deployment
```bash
npx netlify-cli deploy --prod
```
Or just push to `main` branch — Netlify auto-deploys (once GitHub is linked in Netlify dashboard).

## Team
- **Jaz** - Uses Claude Code CLI
- **Sam (whitesam88-collab)** - Uses claude.ai/code (web), owns GitHub repo

Both push to same GitHub repo, Netlify auto-deploys.
