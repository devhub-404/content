# Replaced elements y object fitting

Imágenes, vídeo y algunos controles son replaced elements con dimensiones intrínsecas. `aspect-ratio` aporta una proporción preferida cuando una dimensión es automática y ayuda a reservar una geometría estable antes de que cargue el contenido.

```css
.thumbnail {
  inline-size: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  object-position: 50% 35%;
}
```

`object-fit: cover` llena la caja recortando; `contain` conserva el objeto completo y puede dejar espacio; `fill` puede deformar. `object-position` elige el foco. Evita imponer width y height incompatibles que estiren la imagen: decide cómo debe encajar el contenido.
