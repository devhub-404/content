# Bordes, radius, outlines y shadows

Los bordes ocupan espacio de la caja y `border-radius` redondea borde y background. Los corners redondeados no recortan automáticamente descendientes si el overflow no los clipea. `box-shadow` pinta sombras sin cambiar el tamaño de layout.

```css
.card {
  border: 1px solid rgb(0 0 0 / .15);
  border-radius: 1rem;
  box-shadow: 0 .75rem 2rem rgb(0 0 0 / .18);
}

.card :focus-visible {
  outline: 3px solid Highlight;
  outline-offset: 3px;
}
```

Las outlines no ocupan espacio y son especialmente adecuadas para indicadores de foco. No las elimines globalmente. Bordes y shadows pueden apoyar jerarquía visual, pero los estados importantes deben seguir siendo comprensibles en forced colors o high contrast.
