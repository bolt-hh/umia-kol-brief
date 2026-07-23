# Umia KOL Brief Site — Team Runbook

## What this is
A phone-first, bilingual (EN/KO) single-page microsite that gives an onboarded Umia KOL the whole project in about 20 seconds. Static, no backend. Prepared by Holo Hive.

## Files in this deploy
- `index.html` — the site (self-contained: CSS, JS, logos base64-embedded).
- `vercel.json` — cleanUrls + the `/ko` rewrite.
- `og.png` — link-unfurl card (1200×630). Must sit at the site root.

## Language / links
- Default is English.
- Korean link (hand this to KO KOLs): `https://<domain>/ko`
- Also works: `https://<domain>/?lang=ko` and `https://<domain>/#ko`
- The EN/KO toggle updates the URL live, so a shared link opens in the language shown.

## Deploy (Vercel, team holo-hive)
Option A — drag-drop: zip's three files into Vercel → New Project → drag the folder → Deploy.
Option B — private GitHub repo: push the three files to the repo root, import to Vercel. Jdot pushes; never run git from the mounted folder.
- Enable Vercel Web Analytics (the snippet is already in the page).
- Set a custom domain before any KOL sees it. Never hand out the raw `*.vercel.app` link.

## One thing to swap after the domain is set
`index.html` `<meta property="og:image">` and `twitter:image` are currently relative (`og.png`). Make them absolute — `https://<domain>/og.png` — so the Telegram/X unfurl resolves everywhere. Telegram caches previews; if the link was shared before, bust it with a fresh `?v=2`.

## Pre-launch check (do on a real phone, both languages)
- Toggle EN ↔ KO; confirm KO renders in Noto Sans KR and the URL flips to `/ko`.
- Open `/ko` directly in a fresh tab — it should load in Korean.
- Tap every link row (Website, Umia Score, Docs, Blog, X, Telegram).
- Open the "More detail" expander and the Typical ↔ Umia contrast toggle.
- Confirm the money section shows no unconfirmed token figures and the disclaimer is present.

## Content notes
- Token figures (supply, allocations, auction dates) are intentionally NOT on the page — compliance-safe prose + a link to Docs. If Umia clears figures for KOL use, ask Holo Hive to render them.
- Any copy/stat/link edit is a small change: re-gate through HQC + a link check, not a rebuild.
