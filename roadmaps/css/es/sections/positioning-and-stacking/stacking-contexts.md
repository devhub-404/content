# Stacking contexts y `z-index`

`z-index` no es una única línea numérica global. Los elementos se agrupan en stacking contexts y los hijos se ordenan dentro de su propio contexto. Un hijo con `z-index: 9999` no puede escapar de un contexto ancestral que se pinta por debajo de otro contexto hermano.

```css
:root {
  --z-sticky: 10;
  --z-overlay: 100;
  --z-modal: 110;
}

.site-header {
  position: sticky;
  z-index: var(--z-sticky);
}
```

Posicionamiento con `z-index`, transforms, opacidad, filtros, isolation y algunos tipos de containment pueden crear stacking contexts. Cuando el orden falla, inspecciona esas fronteras en vez de aumentar números sin límite. Una pequeña escala documentada para sticky UI, overlays y modales es más mantenible.
