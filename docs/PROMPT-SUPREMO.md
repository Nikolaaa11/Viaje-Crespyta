# 🛰️ PROMPT SUPREMO — Mapa realista+futurista, aventura total y objetivos

> El brief que gobierna la evolución del sitio de la Crespyta hacia una experiencia de aventura completa: un **mapa holográfico con contorno REAL de Nueva Zelanda**, más trekkings, parques nacionales, deportes extremos y bienestar, y un **tablero de cumplimiento de objetivos**. Hecho con amor. 💛

---

## 0. Reglas de oro (heredadas)
- Protagonista: **Yaritza**, trátala de **"tú"** femenino, cálido. La palabra **"sola" está prohibida** ("una única" en vez de "una sola"). Nada de "ustedes/pareja".
- Presupuesto/arriendo/sueldo/ahorro = **una persona**. Español de Chile, datos y precios NZD 2026 reales.
- **Media anti-roturas:** fotos y videos SOLO con URLs reales verificadas; ante la duda, degradado de respaldo. Ver `MEGA-PROMPT.md` §5–6 para el cheat sheet de componentes y las reglas de media.

## 1. El mapa maestro (realista + futurista) — hecho por Fable 5

**Realismo:** el contorno es el **trazado geográfico REAL** de las dos islas (descargado de un mapa de Wikimedia, precisión reducida a 1 decimal para aligerar, ~100 KB que comprimen muy bien con gzip). Los marcadores se colocan con **proyección equirectangular calibrada** (bounding box real ↔ extremos geográficos: Cabo Reinga −34.4°, Slope Point −46.7°, Fiordland 166.4°E, East Cape 178.55°E) y se **verifican con `SVGGeometryElement.isPointInFill()`** en el navegador para confirmar que caen en tierra.

**Futurismo (consola holográfica):** el mapa vive en un panel oscuro (`.mapconsole`, gradiente noche) con:
- Grilla HUD tenue, **línea de escaneo** animada, esquinas de mira (`.mapcorner`), telemetría ("AOTEAROA · ADVENTURE GRID · 41°S 174°E", "SEÑAL EN VIVO").
- Contorno **neón** (gradiente teal→cyan→violeta) con filtro `feGaussianBlur` glow.
- **Arcos de vuelo** punteados y animados (Auckland→Queenstown, Auckland→Bay of Islands).
- **Pines por categoría** con halo pulsante: 🥾 Trekkings (cyan), 🌲 Parques (verde), 🪂 Aventura (magenta). Label al hover.
- **Filtros interactivos** (`#mapFilters`): Todo / Trekkings / Parques / Aventura togglean `.hide-t/.hide-p/.hide-a`.
- Leyenda clicable en 3 columnas debajo.

**Contrato de ids:** cada pin enlaza a una ficha con id EXACTO. El contenido (Opus) DEBE producir esos ids:
- Trekkings: `trek-rangitoto, trek-waitakere, trek-mauao, trek-tongariro, trek-hooker, trek-roys, trek-routeburn, trek-milford, trek-kepler, trek-rakiura, trek-abel` (+ extras `trek-benlomond, trek-mueller, trek-avalanche, trek-pouakai, trek-reinga, trek-tamaki`).
- Parques: `park-fiordland, park-westland, park-egmont, park-arthurs, park-paparoa`.
- Aventura: `adv-queenstown, adv-rotorua, adv-taupo, adv-waitomo, adv-bayofislands, adv-raglan`.

## 2. Secciones nuevas de contenido (Opus)
- **🌲 Parques nacionales** — 5 fichas `.place.trek` (ids `park-*`), entrada gratis, huts DOC baratos.
- **🪂 Aventura & deportes extremos** — 6 fichas (ids `adv-*`): bungy, skydive, jet boat, black water rafting, buceo, surf; con videos reales y descuentos (bookme.co.nz).
- **🥾 Más trekkings** — 6 fichas extra para completar la colección.
- **🧘 Bienestar (yoga, gym, autocuidado)** — sección nueva `#bienestar`: gimnasios reales de Auckland (Les Mills nació ahí en 1968, CityFitness, Jetts, Snap), estudios de yoga, piscinas/hot pools, parkrun gratis los sábados, y cuidado emocional del migrante (línea 1737). Precios reales 2026 vía búsqueda web.

Cada ficha: `figure.ph` con foto real + `figcaption` con leyenda y crédito, `.stats-row` con chips `.st` (`.st.hard` dificultad, `.st.free` gratis), y `.tags` con `linkbtn` 📍 Mapa (Google Maps) y 🌿 DOC.

## 3. Cumplimiento de objetivos (`#objetivos`) — hecho por Fable 5
Tablero personal e interactivo:
- **Foto redonda** de Yaritza con anillo aurora + medalla (`.obj-photo`), y logo redondo de ella en la nav y el footer (`assets/yaritza.jpg`, con degradado de respaldo).
- **Medidor global** animado (`#objNum` %, `#objBar`) que suma todas las metas.
- **6 grupos** de metas (checklists con guardado en `localStorage`): antes de volar, primeras 2 semanas, Fase 1/2/3 y "bucket list del corazón" (aurora austral, adrenalina, Vía Láctea, ballenas, haka, Hobbiton).
- Cierre con mensaje de amor.

---
*Todo verificado a 2026. Confirmar en fuentes oficiales antes de decidir. Hecho con mucho amor para la Crespyta.*
