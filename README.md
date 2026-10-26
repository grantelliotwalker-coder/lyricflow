# LyricFlow

**A lightweight lyric teleprompter built for live performance.**

👉 **Use it now: [lyricflow-scroller.com](https://lyricflow-scroller.com)**

No accounts, no sign-up, no internet needed once it's loaded. Your songs live on your own device.

---

## What it does

- **Smooth scrolling lyrics.** The current line sits in a glowing band in the middle of the screen, so you always know where you are.
- **Playlists (sets).** Group songs into sets and skip between them on stage with ⏮ ⏭.
- **Per-song settings.** Save each song's scroll speed, font size, line spacing and count-in.
- **4-beat count-in.** An optional 4-3-2-1 countdown before scrolling starts.
- **Drag to adjust.** Drag the lyrics up or down at any time; scrolling picks up again when you let go.
- **Notes.** Keep chords, capo positions and cues with each song.
- **Live editing.** Changes in the editor show up on the stage instantly.
- **Works offline.** After your first visit, it loads with no signal at the venue.
- **Keeps the screen awake** while you're on stage, so your phone or tablet won't dim mid-song.
- **Backup and restore.** Export your songs to a file and import them on any device.

## Getting started

1. Open **[lyricflow-scroller.com](https://lyricflow-scroller.com)** and tap **Stage mode · tap for playlist**.
2. Paste or type your lyrics. Each line scrolls as one line on stage; leave blank lines between verses and choruses.
3. Tap **Save As**, give the song a title and a playlist name (e.g. *Set 1*).
4. Tap **Playlist mode · tap for stage** and press **Start**.

### On stage

| Action | Touch | Keyboard |
| --- | --- | --- |
| Start / pause | Start / Pause buttons | `Space` |
| Back to the first line | Reset | `R` |
| Reposition | Drag the lyrics | — |
| Previous / next song | ⏮ ⏭ | — |
| Speed, font size, spacing, count-in | Settings | — |

**Tip:** with no saved song loaded, Settings become your defaults for new songs. With a song loaded, tap **Save to song** to keep them for that song only.

## Install it like an app (recommended)

Installing gives you a full-screen app icon and makes offline use reliable.

- **iPhone / iPad (Safari):** tap **Share → Add to Home Screen**. Do this on iOS: otherwise Safari may clear your saved songs if you don't visit the site for about a week.
- **Android (Chrome):** tap **⋮ → Install app** (or *Add to Home screen*).
- **Desktop (Chrome / Edge):** click the install icon in the address bar.

## Keeping your songs safe

Songs are saved in your browser on that device only. They don't sync between devices and they aren't uploaded anywhere.

- Use **Edit Playlist → Export** regularly to save a dated backup file (e.g. `lyricflow-backup-2026-10-26.json`).
- Use **Import** to move songs to another device or restore a backup. If songs already exist, you'll be asked whether to replace them.
- Clearing your browser data deletes your songs, so export first.

## For developers

LyricFlow is plain HTML, CSS and JavaScript, with no build step and no dependencies. It's hosted on GitHub Pages.

| File | Purpose |
| --- | --- |
| `index.html` | Stage mode (the teleprompter) |
| `playlist.html` | Lyrics editor and playlist manager |
| `sw.js` | Service worker that makes the app work offline |
| `manifest.webmanifest` | Lets the app be installed |
| `favicon.svg`, `icon-*.png`, `apple-touch-icon.png` | Icons |
| `CHANGES.md` | Release notes |
| `CNAME` | Custom domain for GitHub Pages |

**Run locally:** serve the folder over HTTP (the service worker won't run from `file://`), e.g. `python -m http.server` and open `http://localhost:8000`.

**Releasing an update:** bump `CACHE_VERSION` in `sw.js` (e.g. `lyricflow-v1.1.1`) whenever you change any file, so returning users get the new version.

## Contact & support

- Feature requests, bug reports or just saying hello: **lyricflowscroller@gmail.com**
- LyricFlow is free. If it's helped your performances, you can [buy me a coffee ☕](https://buy.stripe.com/bJe8wQ2lZ5j01Rvd7UgnK01).

© 2026 LyricFlow. All rights reserved.
