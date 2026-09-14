# Hojas de estilo, iconos y enlaces a recursos

El elemento `link` describe una relación entre el documento actual y otro recurso. `rel="stylesheet"` carga CSS y `rel="icon"` aporta un icono para la interfaz del navegador o una instalación del sitio. `link` suele pertenecer a `head` porque describe el documento en lugar de formar parte del contenido visible.

```html
<link rel="stylesheet" href="/styles/site.css">
<link rel="icon" href="/favicon.svg" type="image/svg+xml">
<link rel="preload" href="/fonts/ui.woff2" as="font" type="font/woff2" crossorigin>
```

Pistas como `preload` pueden avisar al navegador de que un recurso importante se necesitará pronto. Son herramientas de rendimiento, no boilerplate. Un preload incorrecto o excesivo puede competir con recursos que el navegador ya priorizaría bien. Añade estas pistas solo cuando adelantar la descarga tenga un beneficio medido.
