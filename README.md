# amautai-portal

Landing y portafolio de aplicaciones de Jonny Otero (instructor SENATI). Vive en [amautai.com](https://amautai.com).

## Stack

- HTML + Tailwind via CDN (sin build step, sin Node)
- Deploy en Cloudflare Pages (gratis, conectado a este repo)
- Headers de seguridad y cache via `_headers` (formato Cloudflare Pages)

## Desarrollo local

Abre `index.html` directo en el navegador o lanza un server estático:

```bash
python -m http.server 8000
# luego abre http://localhost:8000
```

## Estructura

```
amautai-portal/
├── index.html          # Single-page landing
├── _headers            # Cloudflare Pages: cache + security headers
├── assets/
│   ├── logo-amautai.png
│   └── qr_yape.jpeg
├── .gitignore
└── README.md
```

## TODOs antes del deploy

Buscar `TODO:` en `index.html` y completar:

- [ ] Confirmar titular y número Yape (actualmente "Jonny Otero" / 997 348 442)
- [ ] Confirmar/cambiar número Plin
- [ ] Crear cuentas en Ko-fi y Buy Me a Coffee, ajustar URLs
- [ ] Agregar link real de PayPal (`paypal.me/<usuario>`)
- [ ] Agregar link de Mercado Pago
- [ ] Agregar URLs reales de LinkedIn y GitHub en el footer
- [ ] Subir foto del autor (reemplazar las iniciales "JO" en sección Sobre mí)

## Deploy

1. Crear repo `amautai-portal` en GitHub (privado o público)
2. Push de este código
3. Cloudflare Pages → conectar al repo → preset "None" / "static"
4. Configurar dominio: `amautai.com` apunta a `amautai-portal.pages.dev`
