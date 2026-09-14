# Flex containers, items y ejes

`display: flex` o `inline-flex` convierte los hijos directos en flex items. Flexbox es un modelo unidimensional: distribuye items en un eje principal y los alinea en un eje transversal. `flex-direction` decide el eje principal siguiendo writing mode y direction.

```css
.toolbar {
  display: flex;
  align-items: center;
  gap: .75rem;
}
```

Piensa en main/cross axis en vez de asumir siempre horizontal/vertical. Flexbox encaja muy bien en toolbars, navegación, grupos de botones y otras relaciones principalmente lineales. Solo los hijos directos son flex items; sus descendientes mantienen su propio contexto salvo que otra regla lo cambie.
