---
locale: es
status: published
title: "HTML"
slug: html
description: "Una referencia rápida orientada a tareas para sintaxis, APIs y workflows cotidianos de HTML."
tags:
  - html
  - cheatsheet
  - quick-reference
references:
  - label: "MDN: Structuring content with HTML"
    url: https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content
  - label: "MDN: HTML"
    url: https://developer.mozilla.org/en-US/docs/Web/HTML
  - label: "MDN: Responsive images"
    url: https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Responsive_images
---

# HTML

Referencia rápida orientada a tareas. Busca en la página y copia el ejemplo más pequeño que corresponda a lo que necesitas.

## Lenguaje HTML y documento

**Para qué sirve HTML**

```html
<h1>Weather report</h1>
<p>Today will be sunny.</p>
```

**La estructura básica de un documento HTML**

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My page</title>
  </head>
  <body>
    <h1>Hello</h1>
  </body>
</html>
```

**Elementos, etiquetas y elementos vacíos**

```html
<p>This is a paragraph.</p>
<img src="photo.jpg" alt="A mountain at sunrise">
<br>
```

**Atributos y atributos booleanos**

```html
<a href="/about" class="nav-link">About</a>
<button disabled>Save</button>
<input required>
```

**Anidamiento y parsing del navegador**

```html
<p>
  Read the <strong>important note</strong> first.
</p>
```

## Metadatos del documento

**Idioma, charset y viewport**

```html
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
</html>
```

**Título y descripción de la página**

```html
<head>
  <title>Shipping policy — Northwind Books</title>
  <meta
    name="description"
    content="Shipping times, destinations, and return options.">
</head>
```

**Hojas de estilo, iconos y enlaces a recursos**

```html
<link rel="stylesheet" href="/styles/site.css">
<link rel="icon" href="/favicon.svg" type="image/svg+xml">
<link rel="preload" href="/fonts/ui.woff2" as="font" type="font/woff2" crossorigin>
```

**Carga de scripts**

```html
<script src="/scripts/app.js" defer></script>
<script type="module" src="/scripts/main.js"></script>
```

## Semántica de texto y agrupación

**Encabezados y párrafos**

```html
<h1>Gardening guide</h1>
<p>This guide covers vegetables and herbs.</p>

<h2>Vegetables</h2>
<h3>Tomatoes</h3>
<h4>Feeding tomatoes</h4>

<h2>Herbs</h2>
<h3>Basil</h3>
```

**Énfasis e importancia**

```html
<p>You <em>must</em> stir continuously.</p>
<p><strong>Warning:</strong> the surface is hot.</p>
```

**Semántica útil para texto inline**

```html
<p><abbr title="HyperText Markup Language">HTML</abbr> structures web content.</p>
<p>Run <code>npm test</code> and press <kbd>Enter</kbd>.</p>
<p>Water is H<sub>2</sub>O and 2<sup>10</sup> is 1024.</p>
<p>Published <time datetime="2026-09-12">September 12, 2026</time>.</p>
```

**Citas y texto preformateado**

```html
<blockquote>
  <p>The simplest solution was the most reliable.</p>
</blockquote>

<pre><code>function add(a, b) {
  return a + b;
}</code></pre>
```

**Listas**

```html
<ul>
  <li>Tea</li>
  <li>Coffee</li>
</ul>

<ol>
  <li>Open the package.</li>
  <li>Add water.</li>
</ol>

<dl>
  <dt>HTML</dt>
  <dd>Structures web content.</dd>
</dl>
```

**`div`, `span` y agrupación genérica**

```html
<div class="price">
  <span class="amount">$29</span>
  <span class="currency">USD</span>
</div>
```

**Figuras, leyendas y separaciones temáticas**

```html
<figure>
  <img src="sales-chart.png" alt="Sales rise from January through June.">
  <figcaption>Monthly sales, January–June.</figcaption>
</figure>

<hr>
```

## Estructura del documento y landmarks

**`main`, `header` y `footer`**

```html
<body>
  <header>Site header...</header>
  <main>
    <h1>Account settings</h1>
    ...
  </main>
  <footer>Site footer...</footer>
</body>
```

**`nav` y `search`**

```html
<nav aria-label="Primary">
  <a href="/">Home</a>
  <a href="/products">Products</a>
</nav>

<search>
  <form action="/search">
    <label for="q">Search products</label>
    <input id="q" name="q" type="search">
  </form>
</search>
```

**`article`, `section` y `aside`**

```html
<article>
  <h2>Release 4.2 is available</h2>

  <section>
    <h3>Highlights</h3>
    <p>...</p>
  </section>

  <aside>
    <h3>Related links</h3>
    ...
  </aside>
</article>
```

**Jerarquía de encabezados en documentos reales**

```html
<h1>Developer handbook</h1>

<section>
  <h2>Frontend</h2>
  <section>
    <h3>Accessibility</h3>
    <h4>Keyboard support</h4>
  </section>
</section>
```

## Enlaces y navegación

**Enlaces, URLs y texto del enlace**

```html
<a href="/pricing">View pricing</a>
<a href="guide.html">Read the guide</a>
```

**Enlaces de fragmento e IDs**

```html
<a href="#shipping">Jump to shipping</a>

<section id="shipping">
  <h2>Shipping</h2>
  <p>Orders leave within two business days.</p>
</section>
```

**Nuevas pestañas, descargas, correo y teléfono**

```html
<a href="/report.pdf" download>Download report</a>
<a href="mailto:support@example.com">Email support</a>
<a href="tel:+15551234567">Call support</a>
<a href="/help" target="_blank" rel="noopener">Open help in a new tab</a>
```

## Imágenes y medios

**Imágenes y texto alternativo**

```html
<img
  src="mountain.jpg"
  alt="Snow-covered mountain above a pine forest"
  width="1200"
  height="800">
```

**Imágenes responsivas con `srcset`, `sizes` y `picture`**

```html
<img
  src="photo-800.jpg"
  srcset="photo-480.jpg 480w,
          photo-800.jpg 800w,
          photo-1200.jpg 1200w"
  sizes="(width <= 600px) 100vw, 800px"
  alt="A cyclist crossing a stone bridge">

<picture>
  <source media="(width < 600px)" srcset="portrait-crop.jpg">
  <img src="wide-photo.jpg" alt="Chef preparing bread at a work table">
</picture>
```

**Carga de imágenes y prioridad de descarga**

```html
<img
  src="gallery-12.jpg"
  alt="Ceramic bowl with blue glaze"
  width="800"
  height="600"
  loading="lazy">

<img
  src="hero.jpg"
  alt="Team working in the studio"
  fetchpriority="high">
```

**Audio, vídeo, fuentes y pistas**

```html
<video controls poster="preview.jpg">
  <source src="lesson.webm" type="video/webm">
  <source src="lesson.mp4" type="video/mp4">
  <track
    kind="captions"
    src="lesson-en.vtt"
    srclang="en"
    label="English"
    default>
</video>

<audio controls src="interview.mp3"></audio>
```

**Iframes y documentos embebidos**

```html
<iframe
  src="/embedded/map"
  title="Store location map"
  width="640"
  height="400"
  loading="lazy"
  sandbox>
</iframe>
```

## Tablas

**Estructura de tablas y encabezados**

```html
<table>
  <caption>Orders by month</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Orders</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">January</th>
      <td>120</td>
    </tr>
  </tbody>
</table>
```

**Celdas combinadas y tablas complejas**

```html
<table>
  <tr>
    <th rowspan="2">Region</th>
    <th colspan="2">Revenue</th>
  </tr>
  <tr>
    <th>Q1</th>
    <th>Q2</th>
  </tr>
  <tr>
    <th>North</th>
    <td>$42k</td>
    <td>$48k</td>
  </tr>
</table>
```

## Formularios

**Formularios, nombres y envío**

```html
<form action="/search" method="get">
  <label for="q">Search</label>
  <input id="q" name="q" type="search">
  <button type="submit">Search</button>
</form>
```

**Labels, fieldsets y legends**

```html
<label for="email">Email address</label>
<input id="email" name="email" type="email">

<fieldset>
  <legend>Delivery speed</legend>
  <label><input type="radio" name="speed" value="standard"> Standard</label>
  <label><input type="radio" name="speed" value="express"> Express</label>
</fieldset>
```

**Tipos de input textuales**

```html
<input type="text" name="name">
<input type="email" name="email">
<input type="password" name="password">
<input type="search" name="q">
<input type="url" name="website">
<input type="tel" name="phone">
```

**Checkboxes, radio buttons y `select`**

```html
<label><input type="checkbox" name="newsletter"> Newsletter</label>

<label><input type="radio" name="plan" value="basic"> Basic</label>
<label><input type="radio" name="plan" value="pro"> Pro</label>

<select name="country">
  <option value="">Choose a country</option>
  <option value="br">Brazil</option>
  <option value="jp">Japan</option>
</select>
```

**`textarea` y botones**

```html
<label for="message">Message</label>
<textarea id="message" name="message" rows="6"></textarea>

<button type="submit">Send</button>
<button type="button">Preview</button>
```

**Inputs numéricos, de fecha, rango, color y archivo**

```html
<input type="number" name="qty" min="1" max="10" step="1">
<input type="range" name="volume" min="0" max="100">
<input type="date" name="start">
<input type="color" name="accent">
<input type="file" name="receipt" accept="image/*,.pdf">
```

**Validación y autocomplete**

```html
<input
  name="username"
  required
  minlength="3"
  maxlength="20"
  pattern="[A-Za-z0-9_]+"
  autocomplete="username">
```

**`datalist`, `output`, `meter` y `progress`**

```html
<input name="city" list="cities">
<datalist id="cities">
  <option value="Lisbon">
  <option value="Tokyo">
</datalist>

<output>$48</output>
<meter min="0" max="100" value="72">72%</meter>
<progress max="100" value="40">40%</progress>
```

## HTML interactivo

**`details` y `summary`**

```html
<details>
  <summary>Shipping details</summary>
  <p>Orders leave within two business days.</p>
</details>
```

**Diálogos**

```html
<dialog id="confirm-delete">
  <p>Delete this file?</p>
  <form method="dialog">
    <button value="cancel">Cancel</button>
    <button value="delete">Delete</button>
  </form>
</dialog>
```

**Popovers**

```html
<button popovertarget="help">Help</button>

<div id="help" popover>
  <p>Your order number appears on the receipt.</p>
</div>
```

**`hidden` e `inert`**

```html
<section hidden>
  <h2>Draft report</h2>
</section>

<main inert>
  ...
</main>
```

## Scripts, templates y datos personalizados

**`script` y `noscript`**

```html
<script type="module" src="/scripts/main.js"></script>

<noscript>
  <p>This dashboard needs JavaScript for live editing.</p>
</noscript>
```

**`template`, Shadow DOM declarativo y slots**

```html
<template id="task-template">
  <li class="task">
    <span class="task__name"></span>
  </li>
</template>

<article>
  <template shadowrootmode="open">
    <header><slot name="title"></slot></header>
    <slot></slot>
  </template>

  <h2 slot="title">Card title</h2>
  <p>Card body</p>
</article>
```

**`id`, `class` y `data-*`**

```html
<section id="pricing" class="panel featured">
  <button data-product-id="sku-4182">Add to cart</button>
</section>
```

**Dirección, foco y contenido editable**

```html
<html lang="ar" dir="rtl">

<p>User <bdi>إياد</bdi> scored 12 points.</p>

<div id="error-summary" tabindex="-1">
  Please correct the highlighted fields.
</div>

<div contenteditable="true">Edit this note.</div>
```

## Semántica, accesibilidad y calidad

**Primero HTML nativo**

```html
<button type="button">Save changes</button>

<a href="/account">Open account</a>
```

**Nombres accesibles**

```html
<label for="search">Search products</label>
<input id="search" name="q" type="search">

<img src="warning.svg" alt="Warning: high voltage">

<iframe src="/chart" title="Quarterly revenue chart"></iframe>
```

**Orden del código y orden de foco**

```html
<main>
  <h1>Checkout</h1>

  <section>
    <h2>Contact details</h2>
    ...
  </section>

  <section>
    <h2>Payment</h2>
    ...
  </section>
</main>
```

**Validación y depuración de HTML**

```html
<label for="email">Email</label>
<input id="email" name="email" type="email" required>
```
