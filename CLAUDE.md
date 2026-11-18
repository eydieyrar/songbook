# Song Notebook (iPad PWA)
Single-file app: index.html + manifest.json + sw.js + icon.png. No build step, no dependencies. Keep ES5-style JS.
Always bump VERSION in sw.js after any change.
Layout spec: 48x33 grid, lyric block = romaji 1 / Japanese 2 / English 1, gap 1; first page 8 blocks with header, others 9. Header order JP/romaji/EN; lyric order romaji/JP/EN. Do not change these.
Never add song lyrics to the repo. Never build lyric scrapers.
Prefer small line-level patches; explain changes briefly. User dictates by voice; read for intent.
Test on iPad Safari (iOS 16+; container query units are required).
Full background: HANDOFF_song_notebook_app.md
