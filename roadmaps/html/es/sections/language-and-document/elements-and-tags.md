# Elementos, etiquetas y elementos vacíos

La mayoría de los elementos HTML tienen una etiqueta de apertura, contenido y una etiqueta de cierre. En `<p>This is a paragraph.</p>`, la construcción completa es el elemento `p`, mientras que `<p>` y `</p>` son sus etiquetas. Un elemento puede contener texto y otros elementos cuando su modelo de contenido lo permite.

```html
<p>This is a paragraph.</p>
<img src="photo.jpg" alt="A mountain at sunrise">
<br>
```

Algunos elementos son vacíos y no pueden contener contenido ni tener etiqueta de cierre. Entre los más comunes están `img`, `input`, `meta`, `link`, `br`, `hr`, `source` y `track`. Escribir `<img></img>` no convierte una imagen en un contenedor. Conviene aprender las reglas de contenido de cada elemento en vez de asumir que todas las etiquetas vienen en pares.
