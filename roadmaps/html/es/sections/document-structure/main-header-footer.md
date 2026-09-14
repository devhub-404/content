# `main`, `header` y `footer`

`main` identifica el contenido dominante del documento. Una página normalmente tiene una región principal activa; navegación repetida, branding y pie global no pertenecen a ella salvo que sean realmente el propósito central de la página. Esta estructura crea un landmark útil para la navegación asistida.

```html
<body>
  <header>Site header...</header>
  <main>
    <h1>Account settings</h1>
    ...
  </main>
  <footer>Site footer...</footer>
</body>
```

`header` y `footer` son relativos a la sección a la que pertenecen. Una página puede tener cabecera y pie global, mientras que un `article` puede tener su propio header para título y autor y su propio footer para metadatos. Su significado es contextual, no simplemente «la caja de arriba» y «la caja de abajo».
