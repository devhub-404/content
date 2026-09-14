# Feature queries y progressive enhancement

`@supports` prueba si el navegador acepta una sintaxis de propiedad/valor o selector y aplica un bloque condicional. Es útil cuando una mejora requiere varias reglas coordinadas. Para una sola propiedad, a menudo basta con escribir el fallback primero y el valor moderno después.

```css
.component {
  position: absolute;
  inset-block-start: 100%;
}

@supports (position-area: block-end) {
  .component {
    position-area: block-end;
  }
}
```

Progressive enhancement significa que el baseline sigue siendo usable y los navegadores capaces reciben mejoras. Aceptar sintaxis no garantiza ausencia de bugs, así que las funciones críticas necesitan pruebas reales. Prefiere fallbacks basados en estándares a browser sniffing.
