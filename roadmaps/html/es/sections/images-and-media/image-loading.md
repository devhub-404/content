# Carga de imágenes y prioridad de descarga

`loading="lazy"` permite posponer la descarga de una imagen fuera de pantalla hasta que se acerque al viewport. Es útil en páginas largas y galerías, pero normalmente no conviene en la imagen principal visible al cargar porque retrasarla puede empeorar el rendimiento percibido y medido.

```html
<img
  src="gallery-12.jpg"
  alt="Ceramic bowl with blue glaze"
  width="800"
  height="600"
  loading="lazy">

<img
  src="hero.jpg"
  alt="Team working in the studio"
  fetchpriority="high">
```

`fetchpriority` es una pista sobre la prioridad relativa de una petición. Úsala con moderación para recursos que hayas identificado como especialmente importantes o poco importantes. Estas pistas no sustituyen texto alternativo correcto, dimensiones intrínsecas, fuentes responsivas ni optimización de archivos.
