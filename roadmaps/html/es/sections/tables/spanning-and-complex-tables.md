# Celdas combinadas y tablas complejas

`rowspan` y `colspan` permiten que una celda ocupe varias posiciones de fila o columna. Son útiles para encabezados jerárquicos, totales y datos agrupados, pero también aumentan la complejidad de las relaciones. Prefiere la estructura más sencilla que represente los datos correctamente.

```html
<table>
  <tr>
    <th rowspan="2">Region</th>
    <th colspan="2">Revenue</th>
  </tr>
  <tr>
    <th>Q1</th>
    <th>Q2</th>
  </tr>
  <tr>
    <th>North</th>
    <td>$42k</td>
    <td>$48k</td>
  </tr>
</table>
```

En tablas complejas, prueba cómo se anuncia el contexto de encabezados con tecnologías de asistencia. Las asociaciones explícitas con `id` y `headers` existen cuando `scope` no basta. En responsive design, conserva las relaciones: un contenedor con scroll horizontal suele ser más seguro que transformar cada fila en bloques que pierden el contexto de columna.
