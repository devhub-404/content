# `nav` y `search`

`nav` identifica una región de navegación significativa, como el menú principal, un índice o una paginación. No todo grupo de enlaces necesita ser navegación. Si una página tiene varias regiones `nav`, dales nombres accesibles distintos para que puedan diferenciarse.

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

`search` identifica una región destinada a buscar o filtrar. Puede contener un formulario y controles relacionados. El formulario sigue encargándose del envío de datos; `search` describe el propósito general de la región. Los landmarks semánticos ayudan a personas y software a saltar directamente a las áreas principales de una página.
