# Énfasis e importancia

`em` marca énfasis de entonación: cambiar la palabra enfatizada puede cambiar el matiz de una frase. `strong` marca importancia, seriedad o urgencia. Los navegadores suelen mostrar `em` en cursiva y `strong` en negrita, pero esos estilos son solo una presentación por defecto.

```html
<p>You <em>must</em> stir continuously.</p>
<p><strong>Warning:</strong> the surface is hot.</p>
```

Si un texto solo necesita verse distinto, no inventes semántica de énfasis para conseguir cursiva o negrita. Elige el elemento por el significado y después aplica CSS. Esta diferencia importa porque las tecnologías de asistencia y otros programas pueden aprovechar la semántica incluso cuando la presentación visual cambia por completo.
