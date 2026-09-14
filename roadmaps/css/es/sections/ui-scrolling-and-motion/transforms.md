# Transforms

Transforms mueven, rotan, escalan o inclinan la representación de un elemento después del layout. No hacen que las cajas vecinas reserven espacio nuevo. Las propiedades individuales `translate`, `rotate` y `scale` facilitan controlar efectos independientes.

```css
.badge {
  translate: 0 -.15em;
  rotate: -2deg;
}

.button:active {
  scale: .98;
}
```

En una lista `transform`, el orden importa porque cada operación cambia el sistema de coordenadas de la siguiente. `transform-origin` controla el pivote y las transformaciones 3D añaden eje z y perspective. Los transforms suelen crear stacking contexts y el movimiento intenso debe considerar comodidad y accesibilidad.
