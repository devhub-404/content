# Writing modes y propiedades lógicas

CSS usa ejes lógicos para soportar escritura de izquierda a derecha, derecha a izquierda y vertical. El eje inline sigue la progresión del texto y el eje block el apilamiento de líneas. `writing-mode` puede cambiar esos ejes, mientras la dirección semántica del documento normalmente proviene de HTML.

```css
.card {
  inline-size: min(100%, 40rem);
  padding-block: 1rem;
  padding-inline: 1.25rem;
}

.badge {
  inset-block-start: .5rem;
  inset-inline-end: .5rem;
}
```

Propiedades como `inline-size`, `block-size`, `margin-inline`, `padding-block` e insets lógicos expresan geometría según el flujo. Reducen overrides específicos de dirección. Usa `top`, `left` y otras propiedades físicas cuando la relación sea realmente física, no solo porque el diseño inicial era LTR.
