# Shorthands y resets

Las propiedades shorthand configuran varias longhands relacionadas de una sola vez. `margin`, `padding`, `border`, `background`, `font`, `flex`, `grid`, `transition` y `animation` son ejemplos comunes. Resultan útiles cuando quieres expresar el estado completo de un grupo.

```css
.card {
  margin: 1rem 2rem;
  border: 1px solid #ccc;
  background: white;
}
```

Una shorthand también puede resetear longhands que no mencionas explícitamente. Por ejemplo, `background` puede reemplazar valores previos de imagen, posición o repetición. Usa shorthands con intención y conoce las palabras clave globales `initial`, `inherit`, `unset`, `revert` y `revert-layer`, porque cada una vuelve a un punto distinto.
