# Estilizar listas y tablas

La presentación de listas puede controlarse con `list-style-*`, `::marker` y counters sin perder la semántica HTML. Cambia marcadores con CSS en vez de sustituir una lista real por cajas genéricas solo para conseguir control visual.

```css
li::marker {
  color: #2457d6;
  font-weight: 700;
}

table {
  border-collapse: collapse;
  inline-size: 100%;
}

th,
td {
  padding: .75rem;
  text-align: start;
}
```

Las tablas tienen un formatting model especializado con border collapse/spacing, sizing de columnas y alineación de celdas. Estiliza datos realmente tabulares y, en pantallas estrechas, considera scroll horizontal local antes de destruir las relaciones fila/columna convirtiendo todo en bloques.
