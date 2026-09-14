---
locale: en
status: published
title: "HTML"
slug: html
description: "A task-oriented quick reference for everyday HTML syntax, APIs, and workflows."
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

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## HTML Language & Document

**What HTML Is For**

```html
<h1>Weather report</h1>
<p>Today will be sunny.</p>
```

**The HTML Document Skeleton**

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

**Elements, Tags, and Void Elements**

```html
<p>This is a paragraph.</p>
<img src="photo.jpg" alt="A mountain at sunrise">
<br>
```

**Attributes and Boolean Attributes**

```html
<a href="/about" class="nav-link">About</a>
<button disabled>Save</button>
<input required>
```

**Nesting and Browser Parsing**

```html
<p>
  Read the <strong>important note</strong> first.
</p>
```

## Document Metadata

**Language, Charset, and Viewport**

```html
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
</html>
```

**Title and Page Description**

```html
<head>
  <title>Shipping policy — Northwind Books</title>
  <meta
    name="description"
    content="Shipping times, destinations, and return options.">
</head>
```

**Stylesheets, Icons, and Resource Links**

```html
<link rel="stylesheet" href="/styles/site.css">
<link rel="icon" href="/favicon.svg" type="image/svg+xml">
<link rel="preload" href="/fonts/ui.woff2" as="font" type="font/woff2" crossorigin>
```

**Loading Scripts**

```html
<script src="/scripts/app.js" defer></script>
<script type="module" src="/scripts/main.js"></script>
```

## Text & Grouping Semantics

**Headings and Paragraphs**

```html
<h1>Gardening guide</h1>
<p>This guide covers vegetables and herbs.</p>

<h2>Vegetables</h2>
<h3>Tomatoes</h3>
<h4>Feeding tomatoes</h4>

<h2>Herbs</h2>
<h3>Basil</h3>
```

**Emphasis and Importance**

```html
<p>You <em>must</em> stir continuously.</p>
<p><strong>Warning:</strong> the surface is hot.</p>
```

**Useful Inline Text Semantics**

```html
<p><abbr title="HyperText Markup Language">HTML</abbr> structures web content.</p>
<p>Run <code>npm test</code> and press <kbd>Enter</kbd>.</p>
<p>Water is H<sub>2</sub>O and 2<sup>10</sup> is 1024.</p>
<p>Published <time datetime="2026-09-12">September 12, 2026</time>.</p>
```

**Quotes and Preformatted Text**

```html
<blockquote>
  <p>The simplest solution was the most reliable.</p>
</blockquote>

<pre><code>function add(a, b) {
  return a + b;
}</code></pre>
```

**Lists**

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

**`div`, `span`, and Generic Grouping**

```html
<div class="price">
  <span class="amount">$29</span>
  <span class="currency">USD</span>
</div>
```

**Figures, Captions, and Thematic Breaks**

```html
<figure>
  <img src="sales-chart.png" alt="Sales rise from January through June.">
  <figcaption>Monthly sales, January–June.</figcaption>
</figure>

<hr>
```

## Document Structure & Landmarks

**`main`, `header`, and `footer`**

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

**`nav` and `search`**

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

**`article`, `section`, and `aside`**

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

**Heading Hierarchy in Real Documents**

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

## Links & Navigation

**Links, URLs, and Link Text**

```html
<a href="/pricing">View pricing</a>
<a href="guide.html">Read the guide</a>
```

**Fragment Links and IDs**

```html
<a href="#shipping">Jump to shipping</a>

<section id="shipping">
  <h2>Shipping</h2>
  <p>Orders leave within two business days.</p>
</section>
```

**New Tabs, Downloads, Email, and Phone Links**

```html
<a href="/report.pdf" download>Download report</a>
<a href="mailto:support@example.com">Email support</a>
<a href="tel:+15551234567">Call support</a>
<a href="/help" target="_blank" rel="noopener">Open help in a new tab</a>
```

## Images & Media

**Images and Alternative Text**

```html
<img
  src="mountain.jpg"
  alt="Snow-covered mountain above a pine forest"
  width="1200"
  height="800">
```

**Responsive Images with `srcset`, `sizes`, and `picture`**

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

**Image Loading and Fetch Priority**

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

**Audio, Video, Sources, and Tracks**

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

**Iframes and Embedded Documents**

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

## Tables

**Table Structure and Headers**

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

**Cell Spans and Complex Tables**

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

## Forms

**Forms, Names, and Submission**

```html
<form action="/search" method="get">
  <label for="q">Search</label>
  <input id="q" name="q" type="search">
  <button type="submit">Search</button>
</form>
```

**Labels, Fieldsets, and Legends**

```html
<label for="email">Email address</label>
<input id="email" name="email" type="email">

<fieldset>
  <legend>Delivery speed</legend>
  <label><input type="radio" name="speed" value="standard"> Standard</label>
  <label><input type="radio" name="speed" value="express"> Express</label>
</fieldset>
```

**Textual Input Types**

```html
<input type="text" name="name">
<input type="email" name="email">
<input type="password" name="password">
<input type="search" name="q">
<input type="url" name="website">
<input type="tel" name="phone">
```

**Checkboxes, Radio Buttons, and Select**

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

**`textarea` and Buttons**

```html
<label for="message">Message</label>
<textarea id="message" name="message" rows="6"></textarea>

<button type="submit">Send</button>
<button type="button">Preview</button>
```

**Numeric, Date, Range, Color, and File Inputs**

```html
<input type="number" name="qty" min="1" max="10" step="1">
<input type="range" name="volume" min="0" max="100">
<input type="date" name="start">
<input type="color" name="accent">
<input type="file" name="receipt" accept="image/*,.pdf">
```

**Validation and Autocomplete**

```html
<input
  name="username"
  required
  minlength="3"
  maxlength="20"
  pattern="[A-Za-z0-9_]+"
  autocomplete="username">
```

**`datalist`, `output`, `meter`, and `progress`**

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

## Interactive HTML

**`details` and `summary`**

```html
<details>
  <summary>Shipping details</summary>
  <p>Orders leave within two business days.</p>
</details>
```

**Dialogs**

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

**`hidden` and `inert`**

```html
<section hidden>
  <h2>Draft report</h2>
</section>

<main inert>
  ...
</main>
```

## Scripting, Templates & Custom Data

**`script` and `noscript`**

```html
<script type="module" src="/scripts/main.js"></script>

<noscript>
  <p>This dashboard needs JavaScript for live editing.</p>
</noscript>
```

**`template`, Declarative Shadow DOM, and Slots**

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

**`id`, `class`, and `data-*`**

```html
<section id="pricing" class="panel featured">
  <button data-product-id="sku-4182">Add to cart</button>
</section>
```

**Direction, Focus Hooks, and Editable Content**

```html
<html lang="ar" dir="rtl">

<p>User <bdi>إياد</bdi> scored 12 points.</p>

<div id="error-summary" tabindex="-1">
  Please correct the highlighted fields.
</div>

<div contenteditable="true">Edit this note.</div>
```

## Semantics, Accessibility & Quality

**Native HTML First**

```html
<button type="button">Save changes</button>

<a href="/account">Open account</a>
```

**Accessible Names**

```html
<label for="search">Search products</label>
<input id="search" name="q" type="search">

<img src="warning.svg" alt="Warning: high voltage">

<iframe src="/chart" title="Quarterly revenue chart"></iframe>
```

**Source Order and Focus Order**

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

**Validation and HTML Debugging**

```html
<label for="email">Email</label>
<input id="email" name="email" type="email" required>
```
