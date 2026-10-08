<p align="center"><img src="docs/banner.svg" alt="Cathy's Learning Adventure" width="100%"></p>

# Cathy's Learning Adventure

A playful, ever-changing letters, words and math practice game for pre-K through 1st grade. Four levels, spoken questions, a star reward system, and a grown-ups area with real progress tracking. Built as a single-file offline-capable web app (PWA) by LAZLAB Creations.

## Live

| | URL |
|---|---|
| Landing page (one big Play button) | https://johnlaz.github.io/prek/ |
| The app | https://johnlaz.github.io/prek/app/ |

Install it from the app page: **Share → Add to Home Screen** (iPhone/iPad) or **⋮ → Install app** (Android/Chrome).

## What's in the game

- **4 levels**: Little Explorer (3–4), Word Adventurer (4–5), Reading Star (5–6), Rising Champion (6–7).
- **15 skills** per game: letters (upper/lower and matching), starting sounds, sight words, rhyming, syllable claps, numbers, counting, adding, shapes, colors, more-or-less, patterns, opposites, odd-one-out.
- Every question is **read aloud**; wrong answers are spoken back with the right answer.
- Each game is 15 questions. Questions she struggles with come up more often; ones she knows come up less.
- Reading-aloud questions need a grown-up to confirm (**press and hold ✓**), so the results stay honest.

## Grown-ups area

Tap **🔒 Grown-ups** and answer the multiplication question.

- Overall stats, per-skill strengths ("Needs practice" first), last 10 games, suggested next level
- **Settings**: review mix, and **Solo mode** (skips questions that need a grown-up to check)
- **Save / restore a backup** of her progress, copy a text summary, reset

## Repo layout

```
/index.html          landing page (one screen, no scrolling)
/sw.js               landing service worker (also retires the old v1 worker)
/README.md
/docs/banner.svg
/app/index.html      the game (all code and styles in one file)
/app/manifest.json
/app/sw.js           app service worker
/app/icon-192.png
/app/icon-512.png
/app/shot-*.png      screenshots (add when captured, then list them in manifest.json)
```

## AI / model setup

None. The app has no AI features, no accounts and makes no network calls.

## Data & privacy

All progress is stored only in this browser (`localStorage`, key `cathyTrainerStats_v2`). Nothing is uploaded. Use **Save backup** before clearing browser data, switching devices, or removing the home-screen icon (on iPhone/iPad, removing the icon erases its progress).

## Deploy / update

1. Edit `/app/index.html` (and `/index.html` if the landing changes).
2. **Bump the version in two places**: `APP_VERSION` in `/app/index.html` and `CACHE_NAME` in `/app/sw.js` (e.g. `2.1` and `cathy-adventure-v2.1`). The Grown-ups area shows both so you can check they match.
3. Commit and push to `main`; GitHub Pages publishes it. Open the installed app twice and a "new version is ready" bar appears.

## Changelog

**v2.0**
- New one-button landing page; app moved to `/app/`
- Grown-ups gate, hold-to-confirm grading, Solo mode
- Dashboard with per-skill results, history, suggested level; backup/restore
- Spoken feedback; picture-first start screen; SVG shapes; new letter, syllable, addition and odd-one-out questions; answer "tells" removed
- Offline-safe fonts, network-first updates with an update bar, version stamp, zoom and keyboard accessibility

**v1**: first release (single page at the repo root).

---
© 2026 LAZLAB Creations. All Rights Reserved. · lazlab.io@gmail.com
