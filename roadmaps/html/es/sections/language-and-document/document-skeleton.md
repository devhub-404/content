# La estructura básica de un documento HTML

Un documento HTML normal comienza con el doctype, contiene un único elemento raíz `html`, un `head` para los metadatos y un `body` para el contenido que verá el usuario. El doctype no es un elemento HTML: hace que el navegador interprete el documento en modo de estándares.

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My page</title>
  </head>
  <body>
    <h1>Hello</h1>
  </body>
</html>
```

`lang` declara el idioma principal. Dentro de `head`, UTF-8 es la codificación habitual, la declaración de viewport permite el comportamiento responsivo esperado en móviles y `title` da nombre al documento en pestañas y marcadores. El contenido visible pertenece a `body`. Esta estructura es un punto de partida fiable para una página común.
