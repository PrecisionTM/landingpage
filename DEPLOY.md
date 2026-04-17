# Vercel Tirzepatide — Deployment Guide

## ✅ Files to upload to GitHub

```
vercel-tirzepatide/
├─ index.html               ← Tirzepatide landing page (entry point)
├─ styles.css               ← Brand stylesheet
├─ vercel.json              ← Vercel config
├─ DEPLOY.md                ← This file
├─ download                 ← Blank file (required by repo)
└─ images/
   ├─ hero-bg.jpg
   ├─ coach-chris-lane.png
   ├─ final-cta-bg.jpg
   ├─ pharmacy-greenwich.jpg
   ├─ patient-result-1.jpg
   ├─ patient-result-2.jpg
   ├─ doctors/
   │  ├─ dr-palumbo.jpg
   │  ├─ angela-kifer-thomas.jpg
   │  ├─ dr-patel.jpg
   │  ├─ dr-colon-molero.jpg
   │  ├─ samuel-palmer.jpg
   │  ├─ dr-akler.jpg
   │  ├─ brett-whaley.jpg
   │  ├─ michael-gype.jpg
   │  ├─ dr-chandler.jpg
   │  ├─ brittany-umana.jpg
   │  └─ dr-ahmed.jpg
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
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR-ORG/tirzepatide-landing.git
git push -u origin main
```

### 2 — Import in Vercel
1. Go to https://vercel.com/new
2. Click **Import Git Repository** → select your repo
3. **Framework Preset**: `Other`
4. **Root Directory**: *(leave blank)*
5. **Build Command**: *(leave blank)*
6. **Output Directory**: *(leave blank)*
7. **Install Command**: *(leave blank)*
8. Click **Deploy**

### 3 — Done ✅
Vercel detects `index.html` at the root and serves the static site directly. No build step required.

---

## ⚠️ What NOT to do

| Action | Why it breaks |
|---|---|
| Add a `build` script to package.json | Vercel runs it and fails |
| Use `"/(.*)"` rewrite in vercel.json | Intercepts ALL requests including CSS and images |
| Set Root Directory to a subfolder in Vercel | Vercel looks in the wrong place |

---

## 📞 CTA URLs
- Primary CTA: https://precisiontelemed.com/start-weight-loss-program-tirzepatide/
- Sermorelin cross-sell: https://precisiontelemed.com/sermorelin/
