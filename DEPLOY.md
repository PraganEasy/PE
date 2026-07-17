# Deploying to Netlify

This folder is a static site: HTML pages + `support.js` / `image-slot.js` runtimes + real image files under `public/images/…` (SEO-named files — better for search indexing than inlined images).

## Option A — drag & drop (fastest)
1. Go to https://app.netlify.com/drop
2. Drag this whole folder in. Done — you get a live URL immediately.

## Option B — connect to your GitHub repo (PraganEasy/TH) for continuous deploy
1. Copy all files in this folder into the root of the `PraganEasy/TH` repo (or a `site/` subfolder — adjust `publish` in `netlify.toml` if so).
2. Commit and push to `main`.
3. In Netlify: **Add new site → Import an existing project → GitHub → PraganEasy/TH**.
4. Build command: none. Publish directory: `.` (repo root) or wherever you placed the files.
5. Deploy.

## Notes
- `index.html` is the Home page — Netlify serves this at the site root automatically.
- Keep the folder structure intact (`public/images/…`, `support.js`, `image-slot.js`, `.image-slots.state.json`) — pages load these files by relative path.
- Internal links between pages use plain `.html` filenames (e.g. `Plans.html`) — these will resolve correctly once all files sit in the same directory on Netlify.
- Lead forms (Become-Agent, Group-Insurance, Contact) currently submit via `mailto:`. To capture submissions in Netlify instead, add `data-netlify="true"` to each `<form>` and a hidden `form-name` input, per Netlify Forms docs — ask me if you want this wired up.
