# Jerarquía de encabezados en documentos reales

Los encabezados de un documento deben formar una jerarquía legible de `h1` a `h6`. No es necesario usar todos los niveles, pero el nivel debe reflejar el anidamiento. Un encabezado introduce el contenido que sigue hasta que otro encabezado del mismo nivel o superior cambia el contexto.

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

No elijas el nivel por el tamaño visual. Un `h2` puede hacerse pequeño con CSS, mientras que usar `h5` solo porque se ve pequeño crea una jerarquía engañosa. Muchos usuarios de lector de pantalla navegan por la lista de encabezados. Aunque HTML moderno admite varios `h1`, un `h1` principal claro sigue siendo el patrón más sencillo para páginas normales.
