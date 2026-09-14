# Tuples y readonly tuples

Un tuple describe una secuencia con tipos conocidos por posición y, normalmente, longitud conocida. Los labels de elementos mejoran documentación sin cambiar compatibilidad. También pueden existir elementos opcionales o rest.

```ts
type Coordinate = readonly [x: number, y: number];

const point: Coordinate = [10, 20];

function range(): [start: number, end: number] {
  return [0, 100];
}
```

Usa tuples cuando la posición tenga significado estable y el conjunto sea pequeño. Si el caller debe recordar muchas posiciones, un objeto con propiedades nombradas suele ser más claro. `readonly` evita mutación a través de esa referencia y combina bien con `as const`.
