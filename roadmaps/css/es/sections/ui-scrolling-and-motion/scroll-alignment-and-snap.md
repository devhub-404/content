# Alineación de scroll, snap, overscroll y scrollbars

`scroll-padding` reserva un inset de visualización en un scroll container y `scroll-margin` amplía el área de alineación de un destino. Son útiles para anchors y elementos enfocados que podrían quedar debajo de UI sticky. Scroll snap define posiciones preferidas mediante reglas del container y de los items.

```css
html {
  scroll-padding-block-start: 5rem;
}

.carousel {
  display: flex;
  overflow-x: auto;
  scroll-snap-type: inline mandatory;
  overscroll-behavior-inline: contain;
}

.carousel > * {
  scroll-snap-align: start;
}
```

`overscroll-behavior` controla el encadenamiento del scroll en los límites. No ocultes scrollbars solo por estética y evita snap obligatorio en superficies largas de lectura. Una región scrollable debe seguir siendo usable con mouse, touch, teclado y tecnologías de asistencia.
