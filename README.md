# English Word Trainer

A simple, installable web app (PWA) that teaches English spelling to Hindi speakers. Every word shows its Hindi meaning in Devanagari so the learner knows which word to spell.

**Mobile-first**, big tap targets, works offline after the first visit.

## What's inside

- **10 levels, 80 words** — from 3-letter basics ("bag", "box") to business words ("receipt", "discount")
- **Study mode** — see the word, hear it, hear it spelled letter by letter, copy it correctly
- **Test mode** — hear the word, type the spelling, get hints; 80%+ clears the level
- **Price-tag design** — each word shown on a yellow shop price tag with a punched hole
- **Speech** — uses the browser's speech synthesis to pronounce words and spell them out
- **Progress saved** on the phone (localStorage) — streak counter, star ratings, level unlocking
- **Dark mode** follows the phone's setting, reduced-motion respected

## Tech

- Plain HTML / CSS / JS — no framework, no build step
- Everything is inline in `index.html`
- PWA: `manifest.webmanifest`, `sw.js`, icons (192 / 512 / maskable / Apple touch)
- Fonts: Baloo 2 + Noto Sans Devanagari from Google Fonts

## Deploy

### Cloudflare Pages
1. Connect this repo to Cloudflare Pages
2. Build command: *(leave empty)*
3. Build output directory: `/` (the repo root)
4. Deploy

### GitHub Pages
1. Go to repo Settings → Pages
2. Source: Deploy from a branch → `main` → `/ (root)`
3. Save — the site goes live at `https://<username>.github.io/english-word-trainer/`

### Any static host
Just serve the repo root as a static site. All paths are relative, so it works under any sub-path.

## Files

| File | What |
|---|---|
| `index.html` | The complete app (CSS + JS inline) |
| `manifest.webmanifest` | PWA manifest |
| `sw.js` | Service worker (network-first, offline fallback) |
| `icon-192.png` | App icon 192×192 |
| `icon-512.png` | App icon 512×512 |
| `icon-maskable-512.png` | Maskable icon for Android |
| `apple-touch-icon.png` | iOS home screen icon 180×180 |

## Test mode constant

At the top of the `<script>` in `index.html`:

```js
var TEST_UNLOCK_ALL = false;
```

Set to `true` to unlock all 10 levels (useful for testing). The home screen will show a notice.
