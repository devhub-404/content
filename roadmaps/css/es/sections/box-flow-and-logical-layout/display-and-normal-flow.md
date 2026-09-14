# `display` y flujo normal

El flujo normal ya produce un documento usable: cajas block suelen apilarse y el contenido inline participa en líneas de texto. `display` controla cómo una caja participa externamente y qué formatting context crea para sus hijos.

```css
.badge { display: inline-block; }
.toolbar { display: flex; }
.gallery { display: grid; }
.wrapper { display: flow-root; }
```

`inline-block` mantiene participación inline con sizing de caja, `flex` y `grid` crean sus respectivos layouts y `flow-root` crea un block formatting context independiente. `display: none` elimina cajas de la presentación. Usa el modelo que corresponde a la relación real, no el que solo «parece funcionar» en un caso.
