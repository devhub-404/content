# Placement, spans y áreas en Grid

El placement de Grid se basa en líneas. Puedes colocar items con números de línea, nombres, `span` o áreas de template. Los índices negativos cuentan desde el final del grid explícito, por eso `1 / -1` es un patrón común para abarcar todo el ancho.

```css
.page {
  display: grid;
  grid-template:
    "header header" auto
    "sidebar main" 1fr
    / 16rem 1fr;
}

header { grid-area: header; }
aside  { grid-area: sidebar; }
main   { grid-area: main; }

.wide { grid-column: 1 / -1; }
```

`grid-template-areas` hace legibles layouts de regiones, siempre que cada área forme un rectángulo. El placement cambia posición visual, no orden semántico. Mantén el DOM en un orden de lectura y foco correcto aunque Grid coloque las regiones en otra geometría.
