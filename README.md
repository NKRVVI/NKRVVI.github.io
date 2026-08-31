# NKRVVI — Game Programming Portfolio Template

A single-file, dark-themed portfolio template for showcasing game programming work,
split into **Professional Work** and **Personal Projects** sections with a shared
tag filter (Unity / Unreal / Godot / C++ / whatever tags you use). No build step,
no dependencies beyond one Google Fonts link — just `index.html`.

## 1. Put it on GitHub Pages

1. Create a **new repository** on GitHub named exactly:

   ```
   NKRVVI.github.io
   ```

   The name has to match your username exactly (case-insensitive) — this is what
   makes GitHub host it at `https://nkrvvi.github.io` automatically.

2. Add `index.html` to the repo root. Easiest ways:
   - Drag and drop it into the repo via the GitHub web UI ("Add file" → "Upload files"), or
   - From your machine:
     ```bash
     git clone https://github.com/NKRVVI/NKRVVI.github.io.git
     cd NKRVVI.github.io
     # copy index.html into this folder
     git add index.html
     git commit -m "Add portfolio site"
     git push
     ```

3. Go to **Settings → Pages** in the repo. Since the file is already on `main`,
   Pages usually turns itself on automatically for a `username.github.io` repo —
   if not, set Source to the `main` branch, root folder, and save.

4. Wait a minute, then visit `https://nkrvvi.github.io`. Any future push to `main`
   updates the live site.

## 2. Customize the content

Everything you'll want to change lives in `index.html`, marked with comments:

- **Hero section** — your name/tagline/bio and the four links at the top
  (GitHub, itch.io, LinkedIn, email). Swap the `href` placeholders
  (`YOURNAME.itch.io`, `linkedin.com/in/YOURNAME`, `you@example.com`).
- **Professional Work** — one `<article class="project-card">` per project. Each
  has a title, studio name, role, dates, description, tags, and links (store page,
  trailer, etc). Duplicate the block for more projects, delete the extras you don't need.
- **Personal Projects** — same card structure, styled for solo work / jams. The
  `<span class="badge-jam">Game Jam</span>` label is optional — remove it for
  non-jam projects.
- **`data-tags`** on each card drives the filter bar automatically — it's built
  from whatever tags you use, so just keep tags consistent (e.g. always "C#" not
  sometimes "CSharp") and the filter buttons stay in sync with no extra code.
- **Thumbnails** are currently colored gradients with two-letter placeholder text
  (`PT`). Replace a card's `<div class="card-thumb">...</div>` with
  `<img src="path/to/thumb.jpg" alt="...">` and add matching `.card-thumb img
  { width:100%; height:100%; object-fit:cover; }` CSS once you have real
  screenshots — or just customize the gradient/initials for a quick placeholder look.

## 3. Optional polish

- Add real screenshots/thumbnails (see above) — an `assets/` or `images/` folder
  next to `index.html` works fine.
- Add a custom domain later via the same Settings → Pages page if you want
  something other than `nkrvvi.github.io`.
- If the list of projects grows a lot, consider moving card data into a small
  JS array and rendering cards with a loop — the current template intentionally
  keeps everything as plain HTML so it's easy to hand-edit without touching JS.
