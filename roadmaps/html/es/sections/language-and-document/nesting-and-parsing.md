# Anidamiento y parsing del navegador

Los elementos HTML pueden anidarse, pero no cualquier elemento puede ir dentro de cualquier otro. Cierra los elementos anidados en el orden inverso al que se abrieron y respeta el modelo de contenido de cada uno. Un anidamiento correcto hace que el árbol previsto sea claro tanto para personas como para herramientas.

```html
<p>
  Read the <strong>important note</strong> first.
</p>
```

El parser de HTML tolera errores deliberadamente. Cuando el marcado es inválido, el navegador suele repararlo y construir un DOM de todos modos. Por eso el DOM final puede diferir del código fuente, sobre todo con párrafos, tablas, formularios y contenido interactivo. No uses esa recuperación como estilo de programación: ante una estructura extraña, inspecciona el DOM en DevTools y valida el HTML.
