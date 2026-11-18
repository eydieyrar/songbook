# Hosting Song Notebook (GitHub Desktop + GitHub Pages)

Goal: get the app onto a permanent HTTPS link you can open on the iPad and iPhone and install to the Home Screen.
Time: about 20 minutes the first time. Steps marked **YOU** need your own account or password; Claude never enters those.

## The idea in one picture
- **GitHub (website)** = like Google Drive on the web. Stores the project and publishes the app link.
- **GitHub Desktop (PC app)** = like Drive for desktop, with one difference: it does NOT sync by itself. You decide when to upload a "snapshot" (commit + push). Every snapshot is kept, so you can go back to any older version.
- **GitHub Pages** = a free switch on the website that turns the repo's files into a live web link.

## Words you will see
- **Repo (repository):** the project folder, tracked by git.
- **Commit:** a saved snapshot with a short note ("Add furigana toggle").
- **Push:** upload your commits to GitHub. **Pull:** download changes.
- **Branch:** a line of history. You only use `main`.

---

## Part A: one-time setup

1. **YOU** Create a free account at github.com. Pick a username you are happy to show in the link (the app link will be `https://USERNAME.github.io/songbook/`).
2. **YOU** Install GitHub Desktop from desktop.github.com. Open it and sign in to your account.
3. In GitHub Desktop: **File → Add local repository…** and choose the `Songbook` folder.
4. It says "This directory does not appear to be a Git repository". Click **create a repository**.
   - Name: `songbook`
   - Leave Git ignore and License on "None" (a `.gitignore` file is already in the folder).
   - Click **Create repository**.
5. Look at the **Changed files** list on the left. You should see only these (anything else: stop and ask Claude):
   - `index.html`, `manifest.json`, `sw.js`, `icon.png`
   - `CLAUDE.md`, `HOSTING.md`, `.gitignore`
   The files `HANDOFF_song_notebook_app.md`, `Mockup.html` and `mockup-shots` must NOT appear. They contain personal notes and design drafts, and the repo will be public.
6. Bottom left: write `First version` in the Summary box. Click **Commit to main**.
7. Click **Publish repository** (top bar).
   - Name: `songbook`
   - **Untick "Keep this code private"**. Free GitHub Pages needs a public repo. This is safe because the repo holds only the app code, never song lyrics.
   - Click **Publish repository**.
8. **YOU** On github.com open your `songbook` repo → **Settings** → **Pages** (left menu).
   - Source: **Deploy from a branch**
   - Branch: **main**, folder **/ (root)**, then **Save**.
9. Wait about 1 minute and refresh the Pages settings. A box shows "Your site is live at `https://USERNAME.github.io/songbook/`".

## Part B: install on the iPad / iPhone

1. Open the link in **Safari** (not Chrome).
2. Tap **Share → Add to Home Screen → Add**.
3. Open it from the Home Screen icon. It runs full-screen with no browser bars.

IMPORTANT: the Home Screen app has its **own storage**, separate from Safari. Songs you enter in a Safari tab do not appear in the installed app. Install first, then enter songs. If you did enter songs before installing: Backup → copy the text → open the installed app → Backup → paste → Restore.

## Part C: updating after a change

1. Claude changes the files and bumps `VERSION` in `sw.js` (this makes devices load the new version).
2. GitHub Desktop shows the changed files. Check the list looks right.
3. Write a short summary → **Commit to main** → **Push origin**.
4. Wait about 1 minute. On the iPad, close the app fully (swipe it away) and reopen it. If it still looks old, close and reopen once more.

## Safety habits
- **Back up songs often** (Backup screen → Copy). Deleting the Home Screen app deletes its data, and iOS can clear storage of apps it thinks are unused.
- **Never put song lyrics in this repo.** The backup text contains your lyrics, so do not paste it into any public place.
- Optional: make a second, **private** repo `songbook-backup` and save your pasted backup text in it as `backup.json`.
- Changing the icon or manifest later means deleting and re-adding the Home Screen app (back up first).

## Netlify instead?
GitHub Pages is the plan, because you wanted to learn GitHub. Netlify also works and can publish from the same repo. Use one permanent host, not both. For a quick test without any account, dragging the folder onto Netlify Drop gives a temporary link (you did this for the roster app).
