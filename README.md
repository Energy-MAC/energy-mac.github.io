# EMAC Lab Website

Built with [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) and hosted at [energy-mac.github.io](https://energy-mac.github.io).

---

## How to update the site (no coding needed)

### Add a news post
1. Go to `_posts/` → **Add file → Create new file**
2. Name it: `YYYY-MM-DD-short-title.md` (e.g. `2026-09-01-new-paper.md`)
3. Add this header and fill in your content:
```
---
layout: single
title: "Your title here"
date: 2026-09-01
---

Write your news item here in plain text or Markdown.
```
4. Click **Commit** — site rebuilds in ~30 seconds

### Add yourself to the People page
1. Go to `_people/` → **Add file → Create new file**
2. Name it `firstname-lastname.md`
3. Copy this and fill in your details:
```
---
name: "Your Name"
program: "ERG" or "EECS" or "ERG and GSPP" or...
role: "PhD Student", "Master's Student", "Undergrad", or "Postdoc"...
photo: "/assets/img/people/your-name.jpg"
email: "you@berkeley.edu" (optional)
research: "a short (no more than 3 sentences) description of your research"
alumni: false
year: "20XX-"
CV: "cv-your-name.pdf"
---

A short bio paragraph about yourself.
```
4. Add your photo to `assets/img/students/` (square crop works best)
5. Add your CV (if you want) to assets/files/cv-your-name.pdf
6. Commit all files

### Move someone to Alumni
Open their file in `_people/` and change:
```
alumni: true
year: "20xx-20xx"
position: "Their new job title and organization"
degree: "PhD" OR "Master's" or "Bachelor's" or "Postdoc"
```

### Edit research areas or teaching
Edit `_pages/research.md` or `_pages/teaching.md` directly.

---

## File structure
```
_config.yml          ← Site settings (don't edit unless you know what you're doing)
_posts/              ← News items
_pages/              ← Static pages (people, research, teaching, join)
_people/           ← One file per group member
assets/img/ ← Photos
assets/files/ ← Files, like CVs
assets/css/custom.css← Colors and styling
_data/navigation.yml ← Top nav links
```
