# Vercel Tirzepatide — Deployment Checklist

## ✅ What's in this folder

This folder is the **only** thing you push to GitHub / Vercel.

```
vercel-tirzepatide/
├─ index.html               ← Tirzepatide landing page (entry point)
├─ styles.css               ← Brand stylesheet
├─ vercel.json              ← Vercel config (cleanUrls only — no rewrites)
├─ package.json             ← Minimal manifest (no build script)
├─ .gitignore               ← Excludes .vercel/, node_modules/
└─ public/
   └─ images/
      ├─ coach-chris-lane.png
      └─ logos/
         ├─ lecom.svg
         ├─ utmb-health.svg
         ├─ cu-colorado.svg
         ├─ ponce.svg
         ├─ vanderbilt.svg
         ├─ tel-aviv.svg
         ├─ texas-tech.svg
         ├─ cleveland-state.svg
         ├─ maryville.svg
         └─ kentucky.svg
```

---

## 🚀 Deploy to Vercel (step-by-step)

### 1 — Push to GitHub
```bash
# From inside vercel-tirzepatide/ on your machine:
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-ORG/tirzepatide-landing.git
git push -u origin main
```

### 2 — Import in Vercel
1. Go to https://vercel.com/new
2. Click **Import Git Repository** → select `tirzepatide-landing`
3. **Framework Preset**: `Other`
4. **Root Directory**: *(leave blank — repo root IS the site)*
5. **Build Command**: *(leave completely blank)*
6. **Output Directory**: *(leave completely blank)*
7. **Install Command**: *(leave completely blank)*
8. Click **Deploy**

### 3 — Done ✅
Vercel detects `index.html` at the root and serves the static site directly.
No build step. No Node version issues.

---

## ⚠️ What NOT to do

| Action | Why it breaks |
|---|---|
| Add a `build` script to package.json | Vercel runs it, fails if it tries to execute a missing file |
| Use `"/(.*)"` rewrite in vercel.json | Intercepts ALL requests (CSS, images) and returns HTML |
| Set Root Directory to a subfolder in Vercel | Vercel looks in the wrong place |
| Add `engines.node` to package.json | Triggers Node version auto-upgrade warnings |
| Add `now.json` or `.now/` | Conflicts with vercel.json |

---

## 🖼️ Image Paths Used in index.html

All images use paths **relative to the site root**:

| File | Path in HTML |
|---|---|
| Coach photo | `public/images/coach-chris-lane.png` |
| Doctor logos | `public/images/logos/[name].svg` |

---

## 🎨 Design Tokens
- Primary: `#788C75` (sage green)
- Dark: `#3d4a3b`
- Fonts: Cormorant Garamond (headings), Inter (body)

---

## 📞 CTA URLs
- Primary CTA: https://precisiontelemed.com/start-weight-loss-program-tirzepatide/
