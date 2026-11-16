# GOLD Sites – בונה אתרים מקצועי

בונה אתרים בעברית ברמה גבוהה מ-Google Sites.  
כולל: YouTube, גלריות, טפסים, רשתות חברתיות, הטמעת קוד, אנימציות ועוד.

## הרצה מקומית

```bash
npm install
npm run dev
```

## בנייה לפרודקשן

```bash
npm install
npm run build
```

התיקייה `dist/` מוכנה להעלאה.

## העלאה ל-Cloudflare Pages

### אפשרות 1 – העלאה ידנית (הכי פשוטה)

1. הרץ `npm run build`
2. היכנס ל-[Cloudflare Dashboard](https://dash.cloudflare.com) → **Workers & Pages** → **Create** → **Pages** → **Upload assets**
3. העלה את כל תוכן התיקייה `dist/`
4. לחץ **Deploy**

### אפשרות 2 – חיבור ל-Git (מומלץ)

1. העלה את הפרויקט ל-GitHub / GitLab
2. ב-Cloudflare Pages → **Connect to Git**
3. בחר את הריפו
4. הגדרות Build:
   - **Framework preset**: Vite
   - **Build command**: `npm run build`
   - **Build output directory**: `dist`
5. Save and Deploy

### קבצים שכבר מוכנים ל-Cloudflare

- `public/_redirects` – תמיכה ב-SPA (כל הנתיבים חוזרים ל-index.html)
- `index.html` – מוגדר ל-RTL ועברית
- `vite.config.ts` – מוגדר ל-build נקי

## מבנה הפרויקט

```
src/
├── types/blocks.ts       # טיפוסים של כל הבלוקים
├── store/useSiteStore.ts # Zustand + Undo/Redo
├── blocks/               # רנדורים (YouTube, Gallery, Form...)
├── components/editor/    # ספריית בלוקים, Canvas, Properties
└── App.tsx
```

## צבעי המותג

- Background: `#f4efe6`
- Text/Ink: `#1c1917`
- Gold: `#b45309`
