# Figuras, leyendas y separaciones temáticas

`figure` agrupa contenido autocontenido como una imagen, gráfico, ejemplo de código, cita o tabla cuando ese elemento puede tratarse como una unidad. `figcaption` aporta la leyenda y puede aparecer al principio o al final. No toda imagen necesita `figure`; úsalo cuando imagen y leyenda formen una unidad con sentido.

```html
<figure>
  <img src="sales-chart.png" alt="Sales rise from January through June.">
  <figcaption>Monthly sales, January–June.</figcaption>
</figure>

<hr>
```

`hr` representa una ruptura temática, como un cambio de escena o de asunto. La línea horizontal que suelen dibujar los navegadores es solo su estilo por defecto. Si únicamente quieres una separación decorativa entre cajas, una borda en CSS suele ser más adecuada que añadir un `hr` sin significado temático.
