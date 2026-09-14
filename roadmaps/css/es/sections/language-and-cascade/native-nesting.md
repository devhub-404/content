# Nesting nativo de CSS

El nesting nativo permite colocar selectores relacionados y reglas condicionales dentro de una regla padre. Un selector anidado puede empezar por combinador y `&` representa explícitamente el selector exterior cuando necesitas estados o combinaciones más complejas.

```css
.card {
  padding: 1rem;

  > h2 {
    margin-block-start: 0;
  }

  &:hover {
    border-color: #888;
  }

  @media (width >= 40rem) {
    padding: 1.5rem;
  }
}
```

El nesting no cambia la cascada ni elimina la especificidad del selector resultante. Mantén el anidamiento poco profundo para que la relación siga siendo evidente. También puedes anidar `@media` o `@container` dentro de un componente para mantener sus cambios responsivos cerca de sus estilos base.
