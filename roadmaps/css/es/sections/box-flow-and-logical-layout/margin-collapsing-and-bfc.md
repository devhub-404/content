# Colapso de márgenes y block formatting contexts

Margenes en el eje block de cajas normales pueden colapsar en vez de sumarse, incluso entre un padre y su primer o último hijo en ciertas condiciones. Las margenes de items flex y grid no colapsan.

```css
.stack > * + * {
  margin-block-start: 1rem;
}

.isolated {
  display: flow-root;
}
```

Un block formatting context aísla varias interacciones del flujo, incluyendo floats y ciertas relaciones de margen. `display: flow-root` es la forma directa de crear uno. Para ritmo vertical predecible, suele ser más fácil añadir espacio solo entre hermanos adyacentes que usar margenes simétricos en todos los elementos.
