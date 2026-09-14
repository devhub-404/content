# Capas de background y gradientes

Un background puede tener color y varias capas de imagen, cada una con posición, tamaño, repetición, origen y clipping propios. La primera imagen de la lista se pinta más cerca del usuario y el color queda detrás de todas.

```css
.hero {
  background:
    linear-gradient(rgb(0 0 0 / .55), rgb(0 0 0 / .15)),
    url("/images/hero.jpg") center / cover no-repeat;
  color: white;
}
```

Los gradientes lineales, radiales y cónicos son imágenes generadas y pueden combinarse con imágenes normales. `cover` llena la caja y puede recortar; `contain` preserva toda la imagen y puede dejar espacio. Las imágenes de fondo son decorativas: contenido que necesita alt debe estar en HTML.
