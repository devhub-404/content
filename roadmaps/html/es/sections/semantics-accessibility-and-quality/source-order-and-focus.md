# Orden del código y orden de foco

Escribe el HTML en el orden en que una persona debería encontrar el contenido. Grid y Flexbox pueden cambiar la colocación visual, pero normalmente no cambian el orden de lectura del DOM ni el foco secuencial del teclado. Una reordenación visual atractiva puede producir una experiencia de teclado o lector de pantalla desconectada de lo que se ve.

```html
<main>
  <h1>Checkout</h1>

  <section>
    <h2>Contact details</h2>
    ...
  </section>

  <section>
    <h2>Payment</h2>
    ...
  </section>
</main>
```

Usa el DOM como orden canónico de contenido e interacción y deja que CSS cree columnas, sidebars y layouts responsivos que preserven esa lógica. No uses tabindex positivo para reparar un orden de fuente incorrecto. Si el diseño visual exige una secuencia radicalmente distinta, reconsidera el marcado o el diseño en vez de mantener dos órdenes en conflicto.
