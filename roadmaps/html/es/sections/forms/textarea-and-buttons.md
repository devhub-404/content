# `textarea` y botones

`textarea` recoge texto de varias líneas. Su valor inicial se escribe entre las etiquetas, no en un atributo `value`. `rows` y `cols` dan una medida inicial mientras CSS controla normalmente el tamaño final. Recuerda que el whitespace literal dentro del elemento puede formar parte del valor inicial.

```html
<label for="message">Message</label>
<textarea id="message" name="message" rows="6"></textarea>

<button type="submit">Send</button>
<button type="button">Preview</button>
```

Dentro de un formulario, `button` tiene comportamiento de submit por defecto, así que especifica `type` cuando la intención pueda ser ambigua. Usa `submit` para enviar, `button` para acciones controladas por script y `reset` solo cuando restaurar todos los valores realmente ayude al usuario. Fuera de formularios, un botón sigue siendo el elemento correcto para acciones.
