# Imágenes responsivas con `srcset`, `sizes` y `picture`

Las imágenes responsivas resuelven dos problemas distintos. `srcset` con descriptores de anchura y `sizes` permite al navegador elegir una resolución eficiente para el mismo contenido visual según el espacio de renderizado, la densidad de píxeles y otros factores.

```html
<img
  src="photo-800.jpg"
  srcset="photo-480.jpg 480w,
          photo-800.jpg 800w,
          photo-1200.jpg 1200w"
  sizes="(width <= 600px) 100vw, 800px"
  alt="A cyclist crossing a stone bridge">

<picture>
  <source media="(width < 600px)" srcset="portrait-crop.jpg">
  <img src="wide-photo.jpg" alt="Chef preparing bread at a work table">
</picture>
```

`picture` es útil para dirección de arte o cambio de formato. Dirección de arte significa ofrecer un recorte o composición diferente según el layout; cambio de formato permite ofrecer AVIF, WebP u otras alternativas con un `img` de fallback. En ambos casos, `img` sigue siendo el elemento real de la imagen y es quien contiene el texto alternativo.
