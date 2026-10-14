# Puma Suede SS28 · Landing

Prototipo de landing para la Puma Suede, desarrollado para el curso de Marketing Analytics (Business Analytics, 2026).

**Sitio:** https://pipemarting.github.io/puma-suede-ss28/

## Objetivo de negocio (SMART)

Lograr que la Puma Suede SS28 supere en un 5 % la cuota de mercado de su competencia directa, Adidas Samba, al finalizar 2027.

**CTA principal:** "No sigas el ritmo, márcalo. Compra tus Suede".

## Estructura

| Archivo | Qué es |
|---|---|
| `index.html` | Landing autocontenida (imágenes incrustadas). Basada en el wireframe de `docs/wireframe.jpeg`. |
| `docs/gtm-contenedor-puma-suede.json` | Contenedor de Google Tag Manager importable (GA4 + eventos + ecommerce). |

## Medición

- **Google Tag Manager:** `GTM-K4DSS8Q3`, instalado en `<head>` y `<noscript>` tras `<body>`.
- **Consent Mode v2:** todo denegado por defecto; el banner de cookies actualiza `analytics_storage`.
- **Eventos al `dataLayer`** (GTM los envía a GA4):

| Evento | Cuándo |
|---|---|
| `section_view` | Se ve cada sección (`hero`, `por_que_suede`, `comprar`, `banda_final`) |
| `view_item` | Se llega a la ficha de compra (ecommerce GA4) |
| `select_size` | Se elige una talla |
| `add_to_cart` | Clic en "Compra tus Suede" con talla (ecommerce GA4, CLP) |
| `size_missing` | Clic en comprar sin talla |
| `cta_click` | Clic en cualquier CTA o enlace de navegación |
| `scroll_depth` | 25 / 50 / 75 % de la página |
| `select_content` | Cambio de foto en la galería |
| `menu_open` | Apertura del menú |
| `consent_choice` | Aceptar o rechazar cookies |

Embudo sugerido en GA4: `page_view → section_view (por_que_suede) → view_item → select_size → add_to_cart`.

Para depurar, abre el sitio con `?debug` y revisa la consola o GA4 › DebugView.

---
Imágenes de producto: PUMA. Proyecto académico sin fines comerciales.
