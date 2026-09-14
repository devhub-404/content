# `repeat()`, `minmax()` y grids auto-fit

`repeat()` elimina repetición de sintaxis y `minmax()` da límites inferior y superior a una track. Juntos con `auto-fit` o `auto-fill`, Grid puede crear tantas columnas como quepan, produciendo layouts responsivos sin breakpoint de viewport.

```css
.cards {
  display: grid;
  grid-template-columns:
    repeat(auto-fit, minmax(min(16rem, 100%), 1fr));
  gap: 1rem;
}
```

`auto-fit` colapsa tracks vacías para que las existentes se expandan; `auto-fill` conserva los huecos. Un minimum como `min(16rem, 100%)` evita overflow cuando el contenedor completo es más estrecho que el mínimo nominal de una tarjeta.
