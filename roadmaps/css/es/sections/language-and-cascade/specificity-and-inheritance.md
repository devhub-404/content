# Especificidad e herencia

La especificidad compara selectores cuando criterios más fuertes de la cascada empatan. Los IDs pesan más que clases, atributos y pseudo-clases; estos pesan más que selectores de tipo y pseudo-elementos. Los combinadores no añaden especificidad y `:where()` siempre aporta cero.

```css
p { color: black; }
.note { color: navy; }
#warning { color: crimson; }

article {
  color: #333;
  font-family: system-ui;
}
```

La herencia es otro mecanismo. Propiedades de texto como `color` y muchas propiedades tipográficas suelen heredarse; propiedades de layout y caja normalmente no. Mantén selectores con peso razonable para que los overrides normales no necesiten guerras de especificidad.
