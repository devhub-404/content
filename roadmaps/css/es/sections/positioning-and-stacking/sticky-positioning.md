# Posicionamiento sticky

Una caja `sticky` permanece en el flujo normal hasta que el scroll la llevaría más allá de un umbral definido por un inset; entonces queda restringida respecto a su scrollport. Necesita un inset relevante, como `inset-block-start`, para saber cuándo debe pegarse.

```css
.section-title {
  position: sticky;
  inset-block-start: 0;
  background: Canvas;
  z-index: 1;
}
```

El overflow de los ancestros importa porque puede crear el scroll container relevante. Una cabecera sticky también necesita fondo y stacking deliberados para que el contenido que pasa por debajo siga siendo legible. Sticky suele integrarse mejor que `fixed` cuando la persistencia es local a una región.
