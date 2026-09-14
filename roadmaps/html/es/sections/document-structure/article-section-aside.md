# `article`, `section` y `aside`

`article` representa una composición autocontenida como una publicación, noticia, comentario o elemento que tiene sentido de forma independiente. `section` representa un agrupamiento temático dentro del documento y normalmente debería identificarse con un encabezado. Un wrapper usado solo para CSS no se convierte automáticamente en una sección.

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

`aside` representa contenido relacionado con lo que lo rodea pero que no forma parte del flujo principal, como notas, recursos relacionados o una barra complementaria. Estos elementos describen relaciones de contenido, no geometría de pantalla: un aside no tiene que aparecer a un lado y un article no tiene que parecer un artículo periodístico.
