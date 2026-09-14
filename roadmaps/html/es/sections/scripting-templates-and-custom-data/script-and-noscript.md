# `script` y `noscript`

`script` incorpora o carga JavaScript. Prefiere archivos externos para código reutilizable y elige carga clásica, deferida, async o de módulo según las dependencias. Los scripts inline son válidos, pero pueden complicar caché, políticas de seguridad y mantenimiento cuando crecen demasiado.

```html
<script type="module" src="/scripts/main.js"></script>

<noscript>
  <p>This dashboard needs JavaScript for live editing.</p>
</noscript>
```

`noscript` proporciona marcado para entornos donde el scripting relevante está deshabilitado o no disponible. Úsalo cuando la experiencia sin JavaScript necesite una explicación o una alternativa real. Cuando sea posible, renderiza primero contenido y formularios útiles en HTML y mejóralos con JavaScript en vez de dejar una página vacía sin scripts.
