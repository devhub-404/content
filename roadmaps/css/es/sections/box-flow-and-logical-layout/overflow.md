# Overflow y scroll containers

Overflow aparece cuando el contenido no cabe en su caja. `overflow: auto` crea scrolling cuando hace falta, `scroll` lo fuerza, `hidden` recorta con cierto scrolling programático y `clip` realiza un clipping más estricto. Los ejes pueden controlarse por separado.

```css
.code-frame {
  max-inline-size: 100%;
  overflow: auto;
}

.long-token {
  overflow-wrap: anywhere;
}
```

No escondas overflow antes de entender la causa. Un item flex/grid quizá necesite permiso para encogerse, un token largo puede necesitar wrapping o una imagen un max-size. Aplicar `overflow-x: hidden` globalmente suele ocultar un bug de layout en vez de resolverlo.
