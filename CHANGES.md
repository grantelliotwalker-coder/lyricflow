# LyricFlow v1.1 — changes

Copy these files over the repo root. Changed: `index.html`, `playlist.html`.
New: `sw.js`, `manifest.webmanifest`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`.
Every fix is marked with `FIX v1.1` / `NEW v1.1` comments in the code.

## Bug fixes — editor (playlist.html)
- **Save As → Stage showed the Welcome screen.** Saving now tells the stage which song to show and clears the old draft.
- **Changing the title on Save renamed the song instead of copying it.** A new title now saves a copy (keeping notes and settings) and the original stays. The save dialog says which will happen as you type. Rename songs with ℹ in Edit Playlist.
- **↑/↓ reordering did nothing when playlists were mixed.** It now moves within the playlist. ↑ is disabled on the first song and ↓ on the last.
- **Playlist names weren't escaped in the dropdowns.** Names with quotes broke the list, and names with HTML could run script from an imported backup.
- **Draft notes were thrown away on Save As.** They're now kept, and they survive a page reload.
- **Unsaved edits were silently lost when tapping Stage mode.** You're now asked to save first (or stay in the editor). There's also a warning on refresh or closing the tab, and when loading another song over unsaved edits.
- **New songs ignored your stage defaults.** New songs now inherit them instead of fixed values (0.4 / 20px / 1.9).
- **The song position in the details bar counted the whole library.** It now shows the position in the playlist (e.g. 2/8).
- **Deleting the loaded song left the stage pointing at a missing song.** The stage now shows the Welcome screen.
- **Notes and song-settings changes didn't reach the stage until a reload.** They now update live.
- **Import couldn't restore over existing songs.** It now asks whether to replace them, and checks IDs only after cleaning them.
- **Backups overwrote each other.** Export file names are now dated, e.g. `lyricflow-backup-2026-10-26.json`.
- **Renaming a playlist onto an existing name merged them silently.** It now asks first.
- **Songs without an ID got a new random ID on every load.** The ID is now saved once.
- **Stage changes made in another tab could be overwritten.** The editor now reloads when the stage saves (e.g. "Save to song").
- **"Storage full" errors failed silently.** They're now shown.
- **The Stage mode toggle didn't work from the keyboard.** It now responds to Enter and Space.

## Bug fixes — stage (index.html)
- **Dragging mid-song replayed the 4-beat count-in.** It now resumes straight away.
- **Touch drag never resumed scrolling on phones and tablets,** and the status still said "Scrolling". The duplicate touch handlers are removed; pointer events handle touch.
- **Pause or Reset during a count-in didn't stop it,** so scrolling started anyway. Pause now shows during the count-in and cancels it.
- **Dragging had no limits.** It now stops at the first and last lines, so you can't fling the lyrics off-screen.
- **The end-of-song auto-reset could hit the next song.** It's now cancelled if you start, drag or change song within 1.2 seconds.
- **Start after the end did nothing.** It now rewinds to the top.
- **The first line drifted out of the highlight band on resize or rotation.** It now stays aligned.
- **Moving a slider on a saved song overwrote your global defaults.** Defaults now change only when no saved song is loaded. Use "Save to song" for per-song values.
- **"Save to song" could overwrite newer edits from the editor.** It now reloads the songs first.
- **A deleted or missing song ID showed unaligned placeholder text.** It now shows the Welcome screen.
- **The speed readout used 1 decimal place after loading a song.** It's now 2 everywhere.
- **Space/R shortcuts fired while typing in a field.** They're now ignored in form fields.
- **Refreshing the stage lost draft notes.** They're now kept.

## New in v1.1
- **Works offline.** A service worker caches the app after the first visit, so "no internet required" is now true.
- **Installable.** Add to Home Screen on iPhone/iPad, or Install in Chrome/Edge. On iOS this also stops Safari clearing your songs after 7 days without a visit.
- **The screen stays awake** on the stage page (Wake Lock API, where the browser supports it).
- **The app asks the browser to keep your songs** (persistent storage).

## When you release future updates
Bump `CACHE_VERSION` in `sw.js` (e.g. `lyricflow-v1.1.1`) every time you change any file, or returning users keep getting the cached copy. With the update in place, users get the new files on their second visit.
