# main-event-landing

Landing bilingue (IT/EN) di **Main Event**, wrestling manager in pixel art di Little Elsewhere.

- **App**: https://main-event.pages.dev/ (demo motore: `/match`)
- **Landing (dopo il collegamento a Cloudflare Pages)**: https://main-event-home.pages.dev/

## Struttura

`index.html` (IT) · `en/index.html` (EN) · `privacy.html` · `en/privacy.html` · `favicon.svg` · `robots.txt` · `sitemap.xml` · `_headers`

Sito statico zero-dipendenze: nessun build, nessun font esterno (tutto il lettering è pixel art inline).

## Deploy

Cloudflare Pages, project `main-event-home` — build: nessuna, output directory `/`.

## Asset da caricare a mano

Il push binario via API corrompe le immagini: caricare via web (GitHub), esportandole dal Logo Kit (canvas "Main Event — Logo Kit (pixel art)"):

- `apple-touch-icon.png` (180×180, in radice)
- `favicon-32.png` (32×32)
- `og.png` (1200×630, comprimerla sotto i 300 KB con squoosh/tinypng prima di caricarla)
- `icons/icon-192.png`, `icons/icon-512.png`, `icons/maskable-192.png`, `icons/maskable-512.png` (se si vuole il set completo anche sulla landing)

Pubblicare meta e immagini nello stesso momento: se l’og:image va online prima del file, i social cachano "nessuna anteprima" (in caso: bump `?v=N` su og:image/twitter:image).

## Standard

Seguito lo standard PWA & Landing dello studio: bilingue a file separati con hreflang, tema chiaro/scuro condiviso (`main-event-theme`), CSP in Report-Only (da attivare dopo la validazione su deploy di test, sostituendo `unsafe-inline` con gli hash SHA-256 degli script inline), footer solo link reali, Lighthouse mobile ≥ 90.

## Licenza

MIT
