# Esquemas de posicionamiento y containing blocks

`static` mantiene el posicionamiento normal. `relative` deja la caja en flujo pero permite offsets y suele establecer containing block para descendientes posicionados. `absolute` sale del flujo y se posiciona respecto a un containing block; `fixed` suele usar el viewport y `sticky` combina flujo con restricciones de scroll.

```css
.card {
  position: relative;
}

.card__badge {
  position: absolute;
  inset-block-start: .5rem;
  inset-inline-end: .5rem;
}
```

Los offsets solo tienen sentido cuando sabes cuál es el containing block. Ancestros posicionados suelen establecerlo, pero transforms, containment y otras características también pueden hacerlo. Si un elemento absolute aparece donde no esperas, identifica primero su caja de referencia.
