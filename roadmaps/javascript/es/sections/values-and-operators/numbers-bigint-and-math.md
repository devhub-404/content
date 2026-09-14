# Numbers, BigInt y Math

Los Number usan punto flotante IEEE-754 de doble precisión. Los enteros solo son exactos dentro del safe-integer range y muchas fracciones decimales no pueden representarse exactamente en binario. `Number` ofrece helpers de conversión y validación; `Math` reúne funciones y constantes numéricas.

```js
const average = (10 + 15 + 20) / 3;
const rounded = Math.round(average);
const safe = Number.isFinite(rounded);

const huge = 9_007_199_254_740_993n;
```

BigInt usa sufijo `n` y representa enteros sin el límite seguro de Number. Sus operaciones requieren otros BigInt y la división produce resultado entero. Es apropiado para enteros realmente grandes, no para asumir exactitud decimal en dinero; los importes financieros suelen modelarse con unidades menores enteras o aritmética decimal especializada.
