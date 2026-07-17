# 🌏 MEGA-PROMPT MAESTRO — Viaje Crespyta · Auckland 2026

> El brief creativo y técnico que gobierna todo el sitio. Diseño y armazón por **Fable 5**; contenido rico generado por **agentes Opus** en paralelo, uno por sección.

---

## 1. Visión

Una **guía viva, editorial y futurista** para que **Yaritza Cifuentes** (Ingeniera Química, calificación/validación farmacéutica) emigre **SOLA** de Chile a **Auckland, Nueva Zelanda** con Working Holiday Visa. No es un folleto: es el manual con **información privilegiada** — el dato que solo sabe quien ya vivió el proceso — presentado con fotos, videos, guías paso a paso y herramientas interactivas.

**IMPORTANTE — es una guía para ella, hecha con amor:** la protagonista es Yaritza ("la Crespyta"). Todo presupuesto, arriendo, sueldo y ahorro es para **UNA persona** (pieza individual en flat, un solo sueldo). No hay pareja acompañándola ni "partner visa" en el plan inmediato (solo se menciona como opción a futuro). Nunca uses "ustedes", "los dos" ni "pareja". **REGLA ESTRICTA: la palabra "sola" está PROHIBIDA en todo el sitio** (ni "viajando sola", ni "viajera sola", ni "una sola X" — usa "una única X"). El framing es cálido y positivo: la página está *hecha con mucho amor para ella*, no enfatiza que viaja sin compañía.

**Tono:** cercano, chileno, directo, práctico y cariñoso. Trátala a ella de **"tú"** (singular, femenino). Cero relleno: cada frase aporta un dato accionable, un precio, un link o un truco.

## 2. Estrategia del viaje (columna vertebral)

1. **Fase 1 (meses 1–2):** instalarse en 2 semanas + trabajar duro para caja. Findes gratis dentro de Auckland.
2. **Fase 2 (meses 2–4):** escapadas de fin de semana cerca de Auckland; Yaritza asegura trabajo profesional.
3. **Fase 3 (mes 4+):** viajes largos por la Isla Sur con los ahorros; decidir si quedarse (su propia ruta AEWV → residencia; traer a alguien vía partner visa es solo una opción futura).

## 3. Lenguaje de diseño ("Aurora Editorial")

- **Fondo blanco**, tipografía Space Grotesk (display) + Inter (cuerpo) + Fraunces itálica (acentos editoriales).
- Acentos de **aurora del Pacífico**: teal → cyan → violeta → magenta → coral.
- **Fotografía protagonista**, glassmorphism sutil, esquinas redondeadas grandes, sombras suaves, micro-interacciones.
- Secciones alternan fondo blanco / gris muy claro. Mucho aire.

## 4. Principios de contenido

- **Información privilegiada:** nombres concretos, precios exactos en NZD (2026), procedimientos reales, atajos, errores a evitar, "lo que nadie te cuenta".
- **Guías paso a paso** para todo lo procedimental (IRD, banco, visa, buscar pega, comprar auto).
- **Fotos y videos reales y verificados** (ver §6). Nunca inventar URLs.
- **Español de Chile**; nombres propios y términos técnicos en inglés/māori está bien.
- Cada dato sensible enlaza a su **fuente oficial**.

## 5. Cheat sheet de componentes (usar EXACTAMENTE estas clases)

Cada agente devuelve **solo el HTML interior** de su sección: empieza con un `<div class="section-head reveal">` y sigue con el contenido. No incluir `<section>`, `<head>`, `<style>` ni `<script>` (el armazón ya los provee). Añadir `class="reveal"` (y `d1`/`d2`/`d3` para escalonar) a bloques que deban animarse al scroll.

```html
<!-- Encabezado de sección -->
<div class="section-head reveal">
  <span class="eyebrow">Etiqueta</span>
  <h2>Título con <span class="grad-text">acento</span></h2>
  <p class="lead">Bajada de 1–2 frases.</p>
</div>

<!-- Grillas -->
<div class="grid g3 reveal"> … tarjetas … </div>   <!-- g2 / g3 / g4 -->
<div class="split reveal"> <div>izq</div><div>der</div> </div>

<!-- Tarjeta -->
<div class="card">
  <div class="ico a">🎯</div>            <!-- a/b/c/d = variantes de gradiente -->
  <h3>Título</h3>
  <p>Texto.</p>
  <div class="meta"><span><b>Dato:</b> valor</span></div>
  <div class="tip"><b>Truco:</b> …</div>  <!-- opcional -->
</div>

<!-- FOTO con degradado de respaldo (NUNCA se ve rota) -->
<figure class="ph r43" data-label="Sky Tower, Auckland">
  <img src="URL_VERIFICADA" loading="lazy" alt="Descripción" onerror="this.remove()">
  <figcaption>Pie de foto <span class="credit">© Autor / Fuente</span></figcaption>
</figure>
<!-- ratios: r43 (4:3) · r169 (16:9) · r11 (1:1) · r32 (3:2). Variantes de color de respaldo: .ph.b .ph.c .ph.d .ph.n -->

<!-- Galería de fotos -->
<div class="gallery reveal"> <figure class="ph" …>…</figure> × N </div>

<!-- Tarjeta de LUGAR (foto + cuerpo) -->
<div class="places reveal">
  <div class="place">
    <figure class="ph" data-label="Waiheke Island"><img src="…" loading="lazy" alt="…" onerror="this.remove()"></figure>
    <div class="pb">
      <h3>Waiheke Island</h3>
      <p>Descripción breve.</p>
      <div class="tags"><span class="tag">Sin auto ✓</span><span class="price">$46.50</span></div>
    </div>
  </div>
</div>

<!-- Video de YouTube (link-card con miniatura) -->
<div class="videos reveal">
  <a class="video" href="https://www.youtube.com/watch?v=VIDEOID" target="_blank" rel="noopener">
    <span class="vthumb" style="background-image:url(https://img.youtube.com/vi/VIDEOID/hqdefault.jpg)"><span class="play">▶</span><span class="badge">Canal</span></span>
    <span class="vmeta"><b>Título del video</b><span>Por qué verlo</span></span>
  </a>
</div>

<!-- Guía PASO A PASO -->
<ol class="steps reveal">
  <li><div class="s-n">1</div><div class="s-b"><h4>Paso</h4><p>Qué hacer.</p><div class="note">Nota/costo.</div></div></li>
</ol>

<!-- Tabs (para Explorar: Auckland / Findes / Isla Sur) -->
<div class="tabs"><button data-tab="a" class="on">Auckland</button><button data-tab="b">Findes</button></div>
<div class="tabpanel on" data-panel="a"> … </div>
<div class="tabpanel" data-panel="b"> … </div>

<!-- Callouts -->
<div class="callout insider"><div class="ci">💎</div><p><b>Info privilegiada:</b> …</p></div>
<div class="callout tipbox"><div class="ci">💡</div><p>…</p></div>
<div class="callout warn"><div class="ci">⚠️</div><p>…</p></div>

<!-- Acordeón (para detalle largo) -->
<details class="acc reveal"><summary>Título</summary><div class="acc-body"><p>…</p></div></details>

<!-- Empresas (link externo) -->
<div class="companies reveal">
  <a class="company" href="URL" target="_blank" rel="noopener"><div class="cn">Nombre</div><div class="cs">Ubicación · rubro</div><div class="ct">Por qué</div></a>
</div>

<!-- Vocabulario / Decoder -->
<div class="vocab reveal"><div class="row"><span class="term">sweet as</span><span class="def">perfecto</span></div></div>
<div class="decoder reveal"><div class="d"><span class="k">"we'll see"</span><span class="ar">→</span><span class="v">probablemente no</span></div></div>

<!-- Números rápidos -->
<div class="qref reveal"><div class="q"><div class="n">111</div><div class="l">Emergencias</div></div></div>

<!-- Checklist interactivo (se guarda solo en el navegador) -->
<div class="chk-head"><h3>Título</h3><span class="chk-progress">0 / N</span></div>
<div class="checklist reveal" id="chk-UNICO">
  <div class="chk" data-id="id1"><span class="box">✓</span><span class="txt"><b>Tarea</b> — detalle</span></div>
</div>

<!-- Lista de recursos / links -->
<div class="reslist reveal"><a class="res" href="URL" target="_blank" rel="noopener"><span class="ri">🔗</span><span class="rb"><b>Nombre</b><span>Para qué sirve</span></span><span class="arrow">↗</span></a></div>

<!-- Timeline de fases -->
<div class="phases reveal"><div class="phase p1"><span class="num-bg">1</span><span class="badge">Fase 1</span><div class="when">Meses 1–2</div><h3>Título</h3><ul><li>…</li></ul></div></div>

<!-- Cita destacada -->
<p class="pullquote reveal">"Frase memorable con <span class="grad-text">acento</span>."</p>

<!-- Botón-link (mapa / fuente oficial) -->
<a class="linkbtn" href="URL" target="_blank" rel="noopener">📍 Ver en mapa</a>
```

## 6. Reglas de MEDIA (crítico — nada roto)

**Fotos:** usar solo URLs **reales y verificadas** vía búsqueda web. Fuentes recomendadas (permiten hotlink, licencia libre):
- **Wikimedia Commons:** `https://commons.wikimedia.org/wiki/Special:FilePath/NOMBRE_ARCHIVO.jpg?width=1000` (verificar que el archivo existe).
- **Unsplash:** `https://images.unsplash.com/photo-XXXX?w=1000&q=80` (solo IDs reales que aparezcan en resultados de búsqueda).
- Si no hay certeza de que una URL exista, **omitir el `<img>`** y dejar solo `<figure class="ph" data-label="…">` — el degradado de respaldo se ve perfecto. Siempre incluir `loading="lazy"`, `alt` y `onerror="this.remove()"`.

**Videos:** solo YouTube con IDs **reales** obtenidos de resultados de búsqueda web (canales reales: RNZ, TVNZ, Immigration NZ, tourism NZ, creadores kiwis/chilenos en NZ). Miniatura: `https://img.youtube.com/vi/ID/hqdefault.jpg`. Si no hay certeza del ID exacto, usar un **link de búsqueda** `https://www.youtube.com/results?search_query=…` y una `.vthumb` sin `background-image` (queda el degradado nocturno con el ▶).

## 7. Secciones (una por agente Opus)

| id | Sección | Fuente de datos |
|----|---------|-----------------|
| plan | El plan maestro (3 fases + timeline) | síntesis |
| perfil | Yaritza: perfil + empresas objetivo | cv_profile + trabajo-profesional |
| trabajo | Trabajo profesional + rápido, paso a paso | trabajo-profesional + trabajo-rapido |
| ingles | Inglés kiwi: acento, slang, māori, videos | ingles-kiwi |
| llegada | Setup 2 semanas + checklist + salud | setup-llegada + gap-seguro-medico |
| dinero | Presupuesto, envíos, auto, apps | dinero-logistica |
| explorar | Auckland + findes + Isla Sur (tabs, fotos) | auckland-imperdibles + findes-cercanos + viajes-lejanos |
| trekkings | Mapa SVG de NZ + 13 trekkings + galería con leyenda | findes-cercanos + viajes-lejanos |
| cultura | Cultura kiwi + māori + comunidad latina | cultura-kiwi |
| quedarse | Ruta a la residencia + trámites Chile | gap-quedarse + gap-documentos-chile |
| recursos | Directorio de links, apps y grupos | síntesis de todos |

## 8. SÚPER MEGA PROMPT — Sección Trekkings (mapa + fichas + galería con leyenda)

La sección `#trekkings` es la joya visual del sitio. Su estructura:

1. **Mapa SVG estilizado de Nueva Zelanda** (lo provee el armazón, NO lo generan los agentes): ambas islas + Rakiura con gradiente aurora, 13 marcadores numerados con pulso que enlazan a las fichas (`#trek-<id>`), y leyenda clicable con distancia/costo.
2. **Fichas de trekking** (generadas por agentes): tarjetas `.place.trek` con `id` EXACTO para que el mapa enlace. IDs canónicos:
   - Día Isla Norte: `trek-rangitoto`, `trek-waitakere` (Kitekite + Mercer Bay), `trek-mauao`, `trek-tongariro`
   - Día Isla Sur: `trek-hooker`, `trek-roys`, `trek-robroy`, `trek-qthill` (Queenstown Hill)
   - Great Walks: `trek-abel`, `trek-routeburn`, `trek-milford`, `trek-kepler`, `trek-rakiura`
3. **Anatomía de una ficha:**
```html
<div class="place trek" id="trek-roys">
  <figure class="ph" data-label="Roys Peak, Wanaka"><img … onerror="this.remove()"><figcaption>Leyenda real <span class="credit">© Fuente</span></figcaption></figure>
  <div class="pb">
    <h3>6 · Roys Peak</h3>
    <p>Qué es, por qué vale la pena, el dato clave.</p>
    <div class="stats-row"><span class="st">16 km</span><span class="st">5–6 h</span><span class="st">1.200 m ↑</span><span class="st hard">Exigente</span><span class="st free">Gratis</span></div>
    <div class="tags" style="margin-top:10px"><a class="linkbtn" href="https://www.google.com/maps/search/…" target="_blank" rel="noopener">📍 Mapa</a><a class="linkbtn" href="https://www.doc.govt.nz/…" target="_blank" rel="noopener">🌿 DOC</a></div>
  </div>
</div>
```
4. **Chips `.st`:** distancia · tiempo · desnivel · dificultad (`.st.hard` si es exigente) · costo (`.st.free` si es gratis). Datos SOLO de los archivos de investigación — no inventar cifras.
5. **Links por ficha:** siempre un `📍 Mapa` (Google Maps search del track) y un `🌿 DOC` (doc.govt.nz, página oficial del track o del parque; si no hay certeza de la URL exacta, linkear a la búsqueda del sitio DOC).
6. **Galería "Postales de los senderos":** un `.gallery` de 6–9 `figure.ph` con **foto real verificada** y `figcaption` con **leyenda descriptiva + crédito** (© autor/fuente). Si no hay certeza de la URL, dejar la figure sin `<img>` (el degradado + leyenda se ven perfectos).
7. **Extras:** un callout `.insider` (reserva de Great Walks abre en mayo y Milford vuela en minutos; alternativas si se agota) y una guía `.steps` corta "Cómo reservar una Great Walk" (cuenta DOC lista, tarjeta guardada, 9:30 am NZ, fechas alternativas).
8. **Seguridad de montaña** en callout `.warn`: clima alpino cambiante (metservice + adventuresmart.nz), avisar plan a alguien, agua/capas, en invierno Tongariro solo con guía.

---
*Datos verificados a 2026. Confirmar siempre en fuentes oficiales antes de decidir.*
