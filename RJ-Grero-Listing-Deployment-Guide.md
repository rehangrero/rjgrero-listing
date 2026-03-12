# RJ Grero Property Listing — Build & Deploy Guide

## Tech Stack

- React 18
- Vite 5
- Vanilla CSS (no Tailwind)
- Fonts: Cormorant Garamond + Inter (Google Fonts CDN)
- Hosting: Vercel (free tier)

---

## Step 1 — Project Setup

```bash
mkdir rjgrero-listing && cd rjgrero-listing
npm init -y
npm install react react-dom
npm install -D vite @vitejs/plugin-react
```

## Step 2 — File Structure

```
rjgrero-listing/
├── index.html            # Entry HTML (mounts React root)
├── vite.config.js        # Vite config with React plugin
├── package.json          # Dependencies + scripts
├── public/
│   └── images/           # Property images (JPG)
└── src/
    ├── index.jsx          # React DOM render entry
    ├── App.jsx            # Full single-page listing component
    └── App.css            # All styles (responsive, animations, modal)
```

## Step 3 — Configure Vite

**vite.config.js**
```js
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';

export default defineConfig({
  plugins: [react()],
});
```

**package.json scripts**
```json
{
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  }
}
```

## Step 4 — Build the Listing Page

Single-component architecture in `App.jsx` containing:

- Fixed nav bar with scroll-aware transparency
- Full-viewport hero section with property image background
- Stats strip (floor area, views, level, investment grade)
- Property details grid (description + specifications table)
- Photo gallery grid with lightbox modal
- Investment rationale cards
- Risk control protocol strip
- Contact section (phone + email)

All styles in `App.css` with:

- Mobile responsive breakpoints at 900px and 560px
- Fade-up entry animations
- Gold accent brand palette (#B4903C)
- Dark theme (#0B0E14 base)

## Step 5 — Add Property Images

Copy JPGs into `/public/images/` and reference them in the images array inside `App.jsx`:

```js
const images = [
  { url: '/images/IMG-20251002-WA0078.jpg', title: 'Living Pavilion' },
  { url: '/images/IMG-20251002-WA0087.jpg', title: 'Panoramic Outlook' },
  { url: '/images/IMG-20251002-WA0096.jpg', title: 'Master Suite' },
];
```

## Step 6 — Test Locally

```bash
npm run dev
```

Opens at `http://localhost:5173`. Confirm images load, gallery modal works, responsive layout renders correctly.

## Step 7 — Verify Production Build

```bash
npm run build
```

Output goes to `/dist`. Confirm no errors. Preview with:

```bash
npm run preview
```

## Step 8 — Push to GitHub

```bash
git init
git add .
git commit -m "Initial listing page"
git remote add origin https://github.com/rehangrero/rjgrero-listing.git
git branch -M main
git push -u origin main
```

## Step 9 — Deploy to Vercel

1. Go to **vercel.com** and sign in with GitHub
2. Click **"Add New..."** → **"Project"**
3. Select the **rjgrero-listing** repo from the list
4. Vercel auto-detects Vite — no configuration changes needed
5. Click **Deploy**
6. Live URL generated in ~30 seconds

## Step 10 — Connect Custom Domain (Optional)

1. In Vercel project settings → **Domains**
2. Add `listing.rjgrero.com` (or your preferred subdomain)
3. Add a **CNAME** record in your DNS pointing to `cname.vercel-dns.com`
4. SSL auto-provisioned by Vercel

---

## Key Notes

- Any push to `main` on GitHub auto-triggers a new Vercel deployment
- Images in `/public/images/` are served as static assets at the root path
- No backend required — fully static site
- Build output is ~50KB gzipped (React + CSS)
- Free tier covers up to 100GB bandwidth/month
