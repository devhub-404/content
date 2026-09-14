# `nav` and `search`

`nav` identifies a significant navigation region such as the primary menu, table of contents, or pagination. Not every cluster of links needs to be navigation. When a page has more than one navigation landmark, give them distinct accessible labels so users can tell them apart.

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

`search` identifies a region whose purpose is searching or filtering. It can contain a form and related controls. The form still handles data submission; `search` describes the larger purpose of the region. Use semantic landmarks because they help people and software move directly to major page areas.
