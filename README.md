# Ledger — mobile expense tracker

A single-page expense/budget tracker you can host for free on GitHub Pages and use
straight from your phone's browser (you can also "Add to Home Screen" so it opens
like an app).

## 1. Put it on GitHub

1. Go to [github.com/new](https://github.com/new) and create a new repository
   (e.g. `my-ledger`). Public or private both work.
2. Upload `index.html` from this folder into the repo (use "Add file → Upload files"
   on the GitHub website — no command line needed).
3. Commit the change.

## 2. Turn on GitHub Pages

1. In your repo, go to **Settings → Pages**.
2. Under "Build and deployment", set **Source** to `Deploy from a branch`.
3. Set **Branch** to `main` (or whichever branch you uploaded to) and folder to `/ (root)`.
4. Save. After a minute, GitHub will show you a URL like
   `https://yourname.github.io/my-ledger/` — that's your app.

Open that link on your phone and bookmark it (or "Add to Home Screen" for an app-like icon).

## 3. Using it

- Add expenses or income with the form — amount, category, date, note.
- Entries and totals save automatically in your phone's browser, so it works even
  without syncing.
- **Download CSV / Excel** any time from the "Export data" section.

## 4. Syncing to GitHub (optional but recommended)

This makes your data live in the same repo, not just on your phone.

1. Create a personal access token:
   - Go to [github.com/settings/tokens](https://github.com/settings/tokens) →
     "Fine-grained tokens" → "Generate new token".
   - Limit it to **only** the repo you made above.
   - Under permissions, grant **Contents: Read and write**.
   - Generate and copy the token (starts with `github_pat_...`).
2. In the app, open **"Sync to GitHub"**, fill in your GitHub username, repo name,
   branch (`main`), and paste the token.
3. Tap **Save settings**, then **Sync now**.

Your entries will be written to `spending-data.json` in the repo. The token is stored
only in your phone's browser and is only ever sent to `api.github.com`.

> Note: GitHub Pages itself is a static file host — it can't run code to save data
> for you. The sync feature works around this by having your own browser talk
> directly to the GitHub API using your own token. Treat the token like a password;
> if you ever want to revoke it, delete it from the tokens page above.
