# Container queries y unidades de container

Las container queries permiten que descendientes respondan al tamaño de un ancestro en lugar del viewport. `container-type: inline-size` es común para componentes cuya disposición depende del ancho que realmente reciben, y los nombres ayudan a escoger el container correcto.

```css
.card-shell {
  container: card / inline-size;
}

@container card (width >= 32rem) {
  .card {
    display: grid;
    grid-template-columns: 10rem 1fr;
  }
}

.card h2 {
  font-size: clamp(1.2rem, 5cqi, 2rem);
}
```

Unidades como `cqi` y `cqb` escalan respecto al query container. Así el mismo componente puede comportarse bien en una sidebar estrecha y en una región principal ancha. Queries de style o scroll-state son más nuevas y deben usarse con progressive enhancement y comprobación de soporte.
