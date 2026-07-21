# amautai-portal — Landing del ecosistema AmautAI

> Landing estática (HTML + Tailwind via CDN) que vive en `https://amautai.com`.
> Hosting: Cloudflare Workers Static Assets, deploy automático en push a `main`.

## Stack

- HTML5 single-page (`index.html`) + 2 páginas auxiliares (`404.html`, `gracias.html`)
- Tailwind CSS via CDN (sin build step, sin Node)
- Cloudflare Workers via `wrangler.jsonc` (`assets.directory: "./"`)
- SEO: `sitemap.xml`, `robots.txt`, JSON-LD schema.org embedded
- Analytics: Cloudflare Web Analytics (token `3ed0541f056540be927aac0ee940868f`)

## Estructura

```
amautai-portal/
├── index.html          # Single-page landing
├── 404.html            # Custom 404 (servido via wrangler not_found_handling)
├── gracias.html        # Post-donación (acceso via /gracias)
├── sitemap.xml + robots.txt
├── _headers            # Cloudflare security/cache headers
├── _redirects          # amautai.com/demo -> app.amautai.com/auth/demo (302)
├── wrangler.jsonc      # Config del Worker
└── assets/
    ├── logo-amautai.png   # Logo personaje con chullo
    ├── qr_yape.jpeg       # QR Yape para donaciones
    └── foto_jco.jpg       # Foto del autor
```

## Deploy

```bash
git push origin main   # Cloudflare Pages/Workers deploya automático en ~30s
```

Verificar:
```bash
curl -s -o /dev/null -w "%{http_code}\n" https://amautai.com
```

## Contexto completo

El repo de la app principal (CNEB) tiene `CLAUDE.md` + `docs/` con todo
el contexto del ecosistema. Si necesitas más detalle:

- Repo: `automaxtecx-png/amautai` (privado)
- En particular: `docs/bitacora_estrategia.md` (visión + monetización)
- Y `docs/bitacora_deployment.md` (DNS, certs, infra completa)
