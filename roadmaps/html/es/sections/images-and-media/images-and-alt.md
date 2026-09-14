# Imágenes y texto alternativo

`img` incorpora una imagen que forma parte del contenido. `src` identifica el recurso y `alt` ofrece una alternativa textual. El alt correcto depende de la función de la imagen en ese contexto: describe la información que el lector necesita, no el hecho de que «hay una imagen».

```html
<img
  src="mountain.jpg"
  alt="Snow-covered mountain above a pine forest"
  width="1200"
  height="800">
```

Las imágenes puramente decorativas suelen usar `alt=""` para que las tecnologías de asistencia puedan ignorarlas. No omitas `alt` en imágenes de contenido. Definir `width` y `height` intrínsecos permite reservar espacio antes de que cargue la imagen y reduce cambios de layout; CSS todavía puede mostrarla de forma responsiva a otro tamaño.
