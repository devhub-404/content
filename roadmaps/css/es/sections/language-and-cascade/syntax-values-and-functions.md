# Declaraciones, valores, funciones y at-rules

Una declaración combina una propiedad con un valor. Los valores pueden ser keywords, números, longitudes, porcentajes, colores, URLs, imágenes o funciones como `min()`, `calc()`, `rgb()` y `var()`. Estas funciones forman parte de la sintaxis CSS; no son llamadas JavaScript.

```css
@media (width >= 48rem) {
  .card {
    width: min(40rem, 100%);
    color: rgb(20 30 50 / 0.9);
  }
}
```

Las at-rules comienzan con `@` y controlan algo más amplio que una declaración. Algunas envuelven reglas, como `@media`, `@supports`, `@container`, `@layer` y `@scope`; otras definen recursos, como `@font-face` y `@keyframes`. CSS tolera errores: una declaración inválida suele ignorarse sin invalidar todo el archivo.
