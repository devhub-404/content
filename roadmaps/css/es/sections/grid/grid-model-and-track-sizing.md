# Tracks, líneas y `fr` en Grid

Grid es un sistema bidimensional. Filas y columnas son tracks separados por grid lines; su intersección forma celdas y un item puede abarcar varias. Los hijos directos son grid items y pueden ocupar tracks explícitos o implícitos.

```css
.layout {
  display: grid;
  grid-template-columns: 16rem 1fr;
  grid-template-rows: auto 1fr;
  gap: 1rem;
}
```

`fr` distribuye espacio flexible restante después de tamaños fijos, gaps y contribuciones intrínsecas. No es un porcentaje simple. El contenido puede hacer que una track `1fr` crezca más de lo esperado; `minmax(0, 1fr)` es útil cuando quieres permitir que se encoja por debajo de su mínimo intrínseco.
