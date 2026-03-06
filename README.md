# JMD Maçonnerie - Site Node.js multi-pages

Application **Node.js + Express + EJS** multi-pages, maintenable et portable sur tout hébergeur Node.

## Pages
- `/` accueil
- `/prestations`
- `/realisations`
- `/contact`
- `/mentions-legales`
- `/politique-confidentialite`

## Structure
- `server.js` serveur Express (sécurité, perf, SEO technique)
- `config/site.js` configuration globale site
- `config/pages.js` configuration des pages (SEO + breadcrumbs)
- `views/` templates EJS (partials + pages)
- `public/css/styles.css` styles globaux
- `public/js/main.js` front-end (carrousel, galerie, compteurs, RGPD)
- `public/images/` assets

## Axes implémentés
- **SEO avancé**: canonical par page, JSON-LD LocalBusiness + BreadcrumbList, `sitemap.xml`, `robots.txt`
- **Qualité code**: ESLint + Prettier + config pages centralisée
- **Performance**: compression gzip, cache static 7 jours
- **Sécurité**: Helmet (dont CSP), rate limiting, masquage `x-powered-by`
- **Accessibilité**: skip link, landmarks `main`, `aria-*`, focus visible, reduced motion

## Démarrage local
```bash
npm install
npm run dev
```

Puis ouvrir `http://localhost:3000`.

## Commandes utiles
```bash
npm run lint
npm run lint:fix
npm run format:check
npm run format
npm start
```

## Déploiement
Compatible avec toute plateforme supportant Node.js:
- VPS (Nginx + PM2)
- Railway / Render / Fly.io
- Docker/Kubernetes
- Hébergement mutualisé Node.js

Le port est configurable via `PORT` (par défaut `3000`).
`SITE_URL` peut être défini pour l’URL canonique/SEO.
