# Anchor positioning

Anchor positioning permite que un elemento posicionado use otro elemento como ancla geométrica. Es útil para menús, tooltips, callouts y popovers que deben mantenerse unidos a un trigger sin cálculos manuales de posición en JavaScript.

```css
.trigger {
  anchor-name: --menu-trigger;
}

.menu {
  position: absolute;
  position-anchor: --menu-trigger;
  position-area: block-end span-inline-end;
}
```

El modelo incluye placements alternativos para cuando la posición preferida provoca overflow. Es una característica moderna, así que comprueba el baseline exacto y conserva un fallback usable. Resuelve geometría, no la semántica ni el comportamiento de interacción del componente.
