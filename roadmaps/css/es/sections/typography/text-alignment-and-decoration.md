# Alineación y decoración de texto

`text-align` controla alineación inline; `start` y `end` siguen la dirección de escritura y suelen ser más portables que left/right. La justificación modifica espacios para alinear ambos bordes y debe probarse con el idioma y ancho reales.

```css
.article {
  text-align: start;
}

.article a {
  text-decoration-thickness: .08em;
  text-underline-offset: .18em;
}
```

Las propiedades de text decoration controlan línea, estilo, grosor y offset del subrayado. Al personalizar links, conserva una señal reconocible de que son interactivos. Letter spacing, word spacing y text shadows afectan legibilidad, así que no deben usarse solo para forzar un encaje visual.
