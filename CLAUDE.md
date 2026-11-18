# Song Notebook / Songbook (iPad + iPhone PWA)
Single-file app: index.html + manifest.json + sw.js + icon.png. No build step, no dependencies. Keep ES5-style JS.
Always bump VERSION in sw.js after any change.
Digital reading and study app for Japanese songs. The user does NOT handwrite, so the old 48x33 grid/page layout is gone.
Reading view: Apple Music style lyrics (current line sharp, others dimmed; tap a line to make it current; manual only, no audio sync). Line order romaji / Japanese / English. Study mode: hide romaji / Japanese / English, tap a line to reveal.
Planned: Book view (paper feel, paging, furigana), view switch in Settings (Book default on iPad, Lyrics on iPhone), Import song with paste-target selector (Japanese / Romaji / English), song sync with a private repo `songbook-data` (one file per song, fine-grained token, keep mine / theirs / both on conflict).
Data on each device is a cache (localStorage + IndexedDB, newest `savedAt` wins); the Backup screen is the real backup.
Never add song lyrics to this repo (it is public). Never build lyric scrapers. Do not write line-by-line romaji or translations of copyrighted lyrics.
Mock up UI changes first and wait for approval (Mockup.html, ignored by git).
Prefer small line-level patches; explain changes briefly. User dictates by voice; read for intent.
Test on iPad Safari (iOS 16+) and iPhone Safari. Live at https://eydieyrar.github.io/songbook/
Full background: HANDOFF_song_notebook_app.md (old, partly obsolete).
