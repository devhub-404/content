# Wrapping y orden visual

`flex-wrap: wrap` permite crear líneas adicionales cuando los items no caben. Cada línea se dimensiona de forma independiente, así que no crea columnas alineadas entre varias líneas. Cuando filas y columnas necesitan coordinarse, Grid suele ser mejor.

```css
.chips {
  display: flex;
  flex-wrap: wrap;
  gap: .5rem;
}

.featured {
  order: -1;
}
```

`order`, `row-reverse` y `column-reverse` pueden cambiar el orden visual sin cambiar normalmente el orden del DOM ni del foco. Úsalos solo si la secuencia semántica sigue teniendo sentido. Si el contenido realmente debe venir antes, cambia el source en lugar de contar dos historias diferentes.
