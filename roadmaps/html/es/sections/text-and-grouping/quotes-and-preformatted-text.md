# Citas y texto preformateado

`blockquote` representa una cita que forma su propio bloque, mientras que `q` sirve para citas cortas dentro de una línea. Si el lector necesita conocer la fuente, proporciona esa información de manera visible en el contenido cercano, posiblemente con un enlace.

```html
<blockquote>
  <p>The simplest solution was the most reliable.</p>
</blockquote>

<pre><code>function add(a, b) {
  return a + b;
}</code></pre>
```

`pre` conserva espacios y saltos de línea del código fuente, por lo que es útil para código, diagramas ASCII y otros materiales preformateados. Un bloque de código suele combinar `pre` con `code`: `pre` conserva el formato y `code` aporta la semántica de código. Como la indentación dentro de `pre` se vuelve visible, hay que escribirla deliberadamente.
