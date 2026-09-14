# Compatibilidad, entrega progresiva y debugging

CSS está formado por módulos con distintos niveles de madurez y adopción. Que una función aparezca en una especificación no significa que todos los navegadores objetivo implementen exactamente la misma sintaxis o subfeature. Decide qué es requisito, mejora u opcional para tu producto.

```css
.component {
  display: block;
}

@supports (display: grid) {
  .component {
    display: grid;
  }
}
```

Construye un baseline robusto y prueba también el camino mejorado. En DevTools depura por capas: selector, ganador de cascada, valor computado, containing block, algoritmo de layout, overflow, stacking y paint. Añadir `!important`, `position` o `z-index` enormes al azar suele ocultar síntomas en vez de corregir el modelo.
