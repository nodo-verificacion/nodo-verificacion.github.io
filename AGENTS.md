# AGENTS.md — nodo-verificacion.github.io

Instrucciones para cualquier agente que trabaje en este repositorio.

---

## Qué es este repo

Sitio estático de análisis periodístico verificado, publicado via GitHub Pages.
URL: https://nodo-verificacion.github.io

Cada análisis se publica en tres idiomas (ES/EN/PT) con SEO completo para
buscadores tradicionales y crawlers de IA.

---

## Estructura

```
/
  index.html                          ← portada / índice de análisis
  sitemap.xml                         ← sitemap con extensión news + hreflang
  robots.txt                          ← permite todos los crawlers
  assets/style.css                    ← CSS compartido
  google9bbf553ee14f517a.html         ← verificación Google Search Console
  [slug-es]/index.html                ← análisis en español
  en/[slug-en]/index.html             ← análisis en inglés
  pt/[slug-pt]/index.html             ← análisis en portugués
```

---

## Convenciones de slugs

Los slugs se optimizan por idioma según el término de búsqueda dominante en cada mercado:
- ES: nombre/término local  (ej: `gaspi-helicoptero`)
- EN: término en inglés     (ej: `oliver-tree-helicopter-crash`)
- PT: términos combinados   (ej: `acidente-helicoptero-oliver-tree-gaspi`)

---

## SEO requerido en cada página

```html
<html lang="es|en|pt">
<title>keyword principal — secundaria | Nodo Verificación</title>
<meta name="description" content="...">
<meta name="keywords" content="...">
<meta property="og:title">
<meta property="og:description">
<meta property="og:type" content="article">
<meta property="og:url" content="URL canónica de esta versión">
<meta property="article:published_time" content="YYYY-MM-DDT00:00:00Z">
<meta property="article:modified_time" content="YYYY-MM-DDT00:00:00Z">
<link rel="alternate" hreflang="es" href="...">
<link rel="alternate" hreflang="en" href="...">
<link rel="alternate" hreflang="pt" href="...">
<link rel="alternate" hreflang="x-default" href="...versión ES...">
<script type="application/ld+json"> NewsArticle con inLanguage </script>
<link rel="stylesheet" href="[../../]assets/style.css">
```

---

## Sitemap

Cada nuevo análisis requiere 3 entradas nuevas en `sitemap.xml` (ES/EN/PT).
Cada entrada incluye `xhtml:link` para hreflang y bloque `news:news` completo.
No usar comentarios XML — algunos parsers los rechazan.

---

## Portada

Agregar cada nuevo análisis como ítem en `.article-list` en `index.html` raíz.
Campos: kicker, título con link, meta (fecha + estado), resumen, badge.

---

## Análisis publicados

| Tema | Slug ES | Slug EN | Slug PT | Estado |
|---|---|---|---|---|
| Colisión helicópteros Recreio 14/6/2026 | `/gaspi-helicoptero/` | `/en/oliver-tree-helicopter-crash/` | `/pt/acidente-helicoptero-oliver-tree-gaspi/` | Activo |
