# RJ Grero — Rajagiriya Penthouse Listing

Property listing page for the Rajagiriya sky-home. Built with React + Vite.
Brand-matched to [rjgrero.com](https://www.rjgrero.com).

---

## Setup

```bash
# 1. Install dependencies
npm install

# 2. Run locally
npm run dev

# 3. Build for production
npm run build
```

---

## Add Your Property Images

Place your images in the `/public/images/` folder:

```
public/
  images/
    IMG-20251002-WA0078.jpg   ← Living Pavilion (hero)
    IMG-20251002-WA0087.jpg   ← Panoramic Outlook
    IMG-20251002-WA0096.jpg   ← Master Suite
```

Image paths are referenced in `src/App.jsx` under the `images` array.
To add more images, extend the array and update the gallery grid in `App.css`.

---

## File Structure

```
rjgrero-listing/
├── index.html
├── package.json
├── vite.config.js
├── .gitignore
├── public/
│   └── images/          ← Add property photos here
└── src/
    ├── index.jsx        ← React entry point
    ├── App.jsx          ← Main component (all logic)
    └── App.css          ← All styles + responsive
```

---

## GitHub Setup

```bash
git init
git add .
git commit -m "Initial commit — RJ Grero listing page"
git remote add origin https://github.com/YOUR_USERNAME/rjgrero-listing.git
git push -u origin main
```

---

## Brand Colours

| Token       | Hex       | Usage                    |
|-------------|-----------|--------------------------|
| Background  | `#0B0E14` | Page background          |
| Surface     | `#111520` | Section backgrounds      |
| Surface 2   | `#161B27` | Cards                    |
| Gold        | `#B4903C` | Primary accent / CTA     |
| Gold Light  | `#CBA84E` | Hover states             |
| White       | `#F0EDE8` | Body text                |
| Dim         | `#7E8597` | Secondary text           |
| Muted       | `#4A4F62` | Labels / tertiary        |

---

Built for RJ Grero Property Advisory · Colombo, Sri Lanka
