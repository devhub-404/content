# Idioma, charset y viewport

Tres declaraciones pertenecen al inicio de casi todo documento. `lang` identifica el idioma principal y ayuda con pronunciación, traducción, corrección ortográfica y procesamiento dependiente del idioma. `meta charset="utf-8"` indica cómo se interpretan los bytes como caracteres Unicode.

```html
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
</html>
```

La declaración de viewport hace que el viewport de CSS siga el ancho del dispositivo en navegadores móviles y establece una escala inicial normal. Evita configuraciones que impidan el zoom, porque muchos usuarios dependen de él para leer. Si solo una parte del documento cambia de idioma, añade un `lang` específico a esa región en vez de cambiar el idioma de toda la página.
