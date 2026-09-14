# Scroll-driven animations y View Transitions

Las scroll-driven animations usan progreso de scroll o visibilidad como timeline en vez de tiempo transcurrido. Sirven para indicadores de lectura y efectos que realmente correspondan al desplazamiento del usuario.

```css
.reading-progress {
  transform-origin: left;
  animation: grow linear both;
  animation-timeline: scroll(root block);
}

@keyframes grow {
  from { scale: 0 1; }
  to   { scale: 1 1; }
}

.product-card {
  view-transition-name: selected-product;
}
```

View Transitions permiten animar continuidad entre estados mediante snapshots administrados por el navegador y pseudo-elementos dedicados. Ambos sistemas deben ser progressive enhancements: navegación y estado deben seguir siendo correctos sin animación y respetar reduced motion.
