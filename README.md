# Puma Suede SS28 · Landing

Prototipo de landing para la Puma Suede, desarrollado para el curso de Marketing Analytics (Business Analytics, 2026).

**Sitio:** https://pipemarting.github.io/puma-suede-ss28/

## Objetivo de negocio (SMART)

Lograr que la Puma Suede SS28 supere en un 5 % la cuota de mercado de su competencia directa, Adidas Samba, al finalizar 2027.

**CTA principal:** "No sigas el ritmo, márcalo. Compra tus Suede".

## Estructura

| Archivo | Qué es |
|---|---|
| `index.html` | Landing autocontenida (imágenes incrustadas), basada en el wireframe de `docs/wireframe.jpeg`. |
| `docs/difusion-utm.md` | Enlaces UTM por canal y registro de difusión. |

## Modelo de medición

| Brief | Google Analytics 4 |
|---|---|
| Objetivo de negocio | Propiedad **Puma Suede SS28 - Landing** (hora de Chile, CLP) |
| Meta del sitio | Evento `clic_cta_principal` |
| KPI | `clic_cta_principal` marcado como **evento clave** y su tasa por sesión |
| Segmentos | Canal de adquisición, dispositivo y parámetros UTM |

## Implementación

- **Etiqueta de Google (gtag.js):** `G-111X5MEFQZ`, al inicio del `<head>`. Flujo web **Puma Suede SS28 (web)** con medición mejorada activada.
- **CTA principal:** el botón "Compra tus Suede" (`id="cta-principal"`); sus repeticiones "Viste un ícono" y "Quiero mis Suede" llevan `class="cta-principal"`. El script del evento está antes de `</body>`, después de la etiqueta. Los CTA no salen de la página, así que el evento se envía sin perder la visita.
- **Parámetro `ubicacion`:** el `id` de la sección del botón (`inicio`, `comprar`, `banda-final`), registrado como dimensión personalizada.
- **Consent Mode v2:** medición analítica activa salvo que el visitante la rechace; publicidad siempre denegada. No se envían datos personales.
- **Google Tag Manager (`GTM-K4DSS8Q3`):** instalado pero sin etiqueta de GA4, para no duplicar la medición.

Otros eventos enviados por gtag:

| Evento | Cuándo |
|---|---|
| `section_view` | Se ve cada sección |
| `view_item` | Se llega a la ficha de compra (ecommerce GA4) |
| `select_size` | Se elige una talla |
| `add_to_cart` | Compra con talla elegida (ecommerce GA4, CLP) |
| `size_missing` | Clic en comprar sin talla |
| `cta_click` | Clic en cualquier CTA o enlace de navegación |
| `scroll_depth` | 25 / 50 / 75 % de la página |
| `select_content` | Cambio de foto en la galería |
| `menu_open` | Apertura del menú |
| `consent_choice` | Respuesta al banner de cookies |

## Verificación (14 oct 2026)

- [x] Aparecen usuarios en Tiempo real
- [x] Aparece el evento `clic_cta_principal` (con `ubicacion` = `inicio` / `comprar`)
- [x] El ID de medición del sitio (`G-111X5MEFQZ`) coincide con el de la propiedad
- [x] `clic_cta_principal` marcado como evento clave
- [x] Dimensión personalizada **Ubicación CTA** (parámetro `ubicacion`, alcance evento)

La visita de prueba técnica llegó con `utm_source=prueba_tecnica`; exclúyela al analizar.
Los bloqueadores de anuncios impiden el envío de datos: prueba desde el teléfono o una ventana sin extensiones.

## Difusión

Comparte siempre los enlaces con UTM de [`docs/difusion-utm.md`](docs/difusion-utm.md) y anota cada envío en su registro.

Para depurar, abre el sitio con `?debug` y revisa la consola o GA4 › DebugView.

---
Imágenes de producto: PUMA. Proyecto académico sin fines comerciales.
