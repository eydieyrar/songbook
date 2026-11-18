# Songbook (iPad + iPhone PWA)
Single-file app: index.html + manifest.json + sw.js + icon.png. No build step, no dependencies. Keep ES5-style JS.
Always bump VERSION in sw.js (and VER in index.html) after any change.
Digital reading and study app for Japanese songs. The user does NOT handwrite, so the old 48x33 grid/page layout is gone.

Design: native iOS look. Liquid-Glass-style floating tab bar (Songs / Add), glass pills, large titles, System/Light/Dark theme, stack navigation with edge-swipe back (the back button plays the same slide). Settings opens from a gear on the Songs list. Popups (menus, sheets) ease in and out. Segmented controls stand alone (concentric shapes). Match the approved "iOS glass look" tab page in Mockup.html.
Reader: Apple Music style lyrics (current line sharp, others dimmed; tap a line to make it current; no audio sync). Order romaji / Japanese / English. An eye menu at the top right shows or hides each language and stays hidden (persistent); press and hold a hidden bar to peek. Text size is one global setting in Settings.
New song: nothing is added until Save (Cancel asks Discard / Keep editing). Editing an existing song autosaves.
Lyric entry: three paste fields (Japanese / Romaji / English), each with an optional source link and a search menu (Google, Uta-Net, Genius open in a new tab). The user pastes lyrics. "Apply" fills lines by position. Alignment card shows per-language counts. Each row type (RO/JP/EN) has its own up/down and a clear-to-blank (no pull-up).
Covers: Find covers uses the Apple Music (iTunes Search) catalogue and Spotify oEmbed; the song stores only the image URL.

Sync: private repo `songbook-data` (one file per song, songs/<id>.json) through the GitHub API with a fine-grained token kept only on the device (localStorage key songbook.sync, never in backups). Conflict per song: keep mine / theirs / both. Device data is a cache (localStorage + IndexedDB, newest savedAt wins); the Backup screen is the real backup. The service worker must never cache cross-origin requests.

Rules: never add song lyrics to this repo (it is public). Never build lyric scrapers or fetch lyrics from sites. Do not write line-by-line romaji or translations of copyrighted lyrics.
Mock up UI changes first (Mockup.html, ignored by git) and wait for approval.
Prefer small line-level patches; explain changes briefly. User dictates by voice; read for intent.
Test on iPhone 13 mini (karaoke) and iPad mini (home study) Safari / Home Screen app. Live at https://eydieyrar.github.io/songbook/
