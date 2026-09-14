# Pseudo-elementos y contenido generado

Los pseudo-elementos permiten estilizar partes generadas o abstractas de un elemento. `::before` y `::after` pueden generar presentación con `content`; `::marker` alcanza marcadores de listas y `::selection` el texto seleccionado.

```css
.tag::before {
  content: "#";
  opacity: .6;
}

li::marker { font-weight: 700; }

::selection {
  background: Highlight;
  color: HighlightText;
}
```

No pongas instrucciones o etiquetas esenciales solo en contenido generado, porque su propósito principal es presentacional. Los pseudo-elementos pueden formar cajas reales y participar en posicionamiento, stacking y overflow, así que deben tratarse con la misma disciplina de layout que otras cajas.
