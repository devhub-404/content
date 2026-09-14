# Dirección, foco y contenido editable

`dir` expresa la dirección base del texto y pertenece al HTML cuando esa dirección se conoce por el contenido. `bdi` puede aislar texto de dirección desconocida para que no altere el texto bidireccional que lo rodea. La dirección es información semántica; después CSS puede adaptar el layout mediante propiedades lógicas.

```html
<html lang="ar" dir="rtl">

<p>User <bdi>إياد</bdi> scored 12 points.</p>

<div id="error-summary" tabindex="-1">
  Please correct the highlighted fields.
</div>

<div contenteditable="true">Edit this note.</div>
```

`tabindex="-1"` hace que un elemento pueda recibir foco por programación sin añadirlo al orden normal de Tab; `0` puede incluir un objetivo apropiado en el orden secuencial. Evita valores positivos porque crean un orden alternativo frágil. `contenteditable` hace contenido editable, pero no proporciona un editor completo: selección, pegado, sanitización, undo, almacenamiento y accesibilidad siguen necesitando diseño.
