# Semántica útil para texto inline

HTML incluye elementos inline para tipos de texto comunes. `abbr` identifica abreviaturas; `code`, código; `kbd`, entrada del usuario; `samp`, salida de un programa; `sub` y `sup`, subíndice y superíndice cuando forman parte del significado; y `time` puede combinar texto legible con una fecha u hora legible por máquinas.

```html
<p><abbr title="HyperText Markup Language">HTML</abbr> structures web content.</p>
<p>Run <code>npm test</code> and press <kbd>Enter</kbd>.</p>
<p>Water is H<sub>2</sub>O and 2<sup>10</sup> is 1024.</p>
<p>Published <time datetime="2026-09-12">September 12, 2026</time>.</p>
```

Otros elementos útiles son `mark` para resaltar algo relevante al contexto, `small` para comentarios secundarios como texto legal, `cite` para el título de una obra y `q` para una cita corta dentro de una línea. Elige estos elementos por su significado, no simplemente porque su estilo por defecto resulte conveniente.
