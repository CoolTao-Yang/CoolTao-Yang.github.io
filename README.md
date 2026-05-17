# Zetao Yang — Personal Homepage

A minimal, static academic homepage. Pure HTML + CSS, no build step.

Live URL after deployment: **https://CoolTao-Yang.github.io**

---

## File structure

```
personal_site/
├── index.html        # Main page (edit this for content)
├── style.css         # Styling
├── README.md         # This file
└── assets/
    └── profile.jpg   # Your photo (you need to add this)
```

---

## Local preview

Just **open `index.html` in any browser** — double-click in Windows Explorer is fine.

The page is self-contained (no JS, no external fonts). What you see locally is what GitHub Pages will serve.

---

## Deployment to GitHub Pages

### Option A: Repo named `CoolTao-Yang.github.io` (gets root URL)

1. Create a new public repo on GitHub named exactly **`CoolTao-Yang.github.io`**.
2. From this folder, run:
   ```bash
   git init
   git add .
   git commit -m "init personal homepage"
   git branch -M main
   git remote add origin https://github.com/CoolTao-Yang/CoolTao-Yang.github.io.git
   git push -u origin main
   ```
3. Within 1–2 minutes, visit `https://CoolTao-Yang.github.io` — site is live.

### Option B: Repo with any name (gets sub-path URL)

If you'd rather call the repo something else (e.g. `homepage`):
1. Create public repo `CoolTao-Yang/homepage`.
2. Push same as above.
3. In repo Settings → Pages → set Source to `main` branch / root.
4. URL becomes `https://CoolTao-Yang.github.io/homepage/`.

**Option A is cleaner** (no sub-path), recommended.

---

## What to update

### 1. Add your photo

Put a square or portrait JPG/PNG at `assets/profile.jpg`. Recommended:
- Size: 600×720 px or similar 5:6 ratio
- Format: JPG (smaller file size than PNG for photos)
- Style: head & shoulders, plain background

If you don't add one, the page renders a "photo" placeholder box instead.

### 2. Things you should fill in / verify

Search `index.html` for these and replace with real values:

- **Email**: currently `zetao2100@gmail.com` — may update to `zetao.yang@e.ntu.edu.sg` after NTU enrolment.
- **arXiv link**: `https://arxiv.org/abs/2605.10547` — confirm this is correct after the paper is fully indexed.
- **Niu Lingfeng UCAS page**: hardcoded to a guessed URL. Replace with real faculty page link, or remove the hyperlink.
- **LinkedIn**: not currently shown anywhere. When you set up LinkedIn, add a `<a href="...">LinkedIn</a>` to the `.contacts` div in `index.html`.

### 3. Future updates

- **Add news**: New news item → edit the `<ul class="news-list">` in `index.html`.
- **Add publication**: Duplicate a `<div class="pub">` block.
- **Add experience/award/activity**: Find the relevant section and add a new entry.

Each edit → `git add . && git commit -m "..." && git push` → site updates automatically.

---

## Customising the design

- **Colours**: Edit the `:root { --accent: ... }` block at the top of `style.css`.
  - Currently: deep blue `#1f4e79` for accents, warm red `#c0392b` for hover.
- **Font**: System fonts (no web font loaded). To use Inter/Source Sans/etc., add
  a `<link>` in `<head>` and update the `font-family` in `body`.
- **Layout width**: `max-width: 1100px` in `.layout` — increase/decrease as desired.
- **Sidebar width**: `flex: 0 0 180px` in `.sidebar`.

---

## Why plain HTML and not Jekyll / Hugo?

- **Zero build step**: Edit, push, done. No `bundle install`, no Ruby, no theme breakage.
- **Easy debugging**: Open file in browser, inspect.
- **GitHub Pages auto-hosts** `index.html` directly — no `gh-pages` workflow needed.
- **For a single-person homepage**, the maintenance overhead of Jekyll/AcademicPages isn't worth it.

If your needs grow (blog with multiple posts, paginated lists, taxonomies), migrate
to Jekyll then.
