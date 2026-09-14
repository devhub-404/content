# Estructura de tablas y encabezados

Usa tablas para datos cuyo significado depende de filas y columnas. `table` contiene filas `tr`, y cada fila contiene celdas de datos `td` o encabezados `th`. `caption` da nombre a la tabla. `thead`, `tbody` y `tfoot` pueden agrupar filas en regiones lógicas.

```html
<table>
  <caption>Orders by month</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Orders</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">January</th>
      <td>120</td>
    </tr>
  </tbody>
</table>
```

Los `th` deben representar encabezados reales de fila o columna. `scope="col"` y `scope="row"` hacen explícitas relaciones simples y ayudan a tecnologías de asistencia a dar contexto al navegar por las celdas. No simules una tabla de datos con cajas genéricas, y no uses una tabla HTML solo para maquetar una página.
