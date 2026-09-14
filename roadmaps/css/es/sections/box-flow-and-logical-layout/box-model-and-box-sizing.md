# Box model y `box-sizing`

Una caja CSS tiene áreas de contenido, padding, borde y margen. Con `content-box`, el tamaño declarado describe el contenido y padding/borde se suman. Con `border-box`, el tamaño declarado ya incluye padding y borde, por eso suele ser un baseline más fácil de razonar.

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

.card {
  inline-size: 20rem;
  padding: 1rem;
  border: 1px solid #ccc;
  margin-block: 1rem;
}
```

Padding crea espacio dentro del borde y margin fuera de él. Los fondos pintan determinadas áreas de la caja, mientras el margen permanece transparente. Cuando una caja resulta más grande de lo esperado, inspecciona el box model en DevTools antes de cambiar números al azar.
