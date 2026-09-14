# Atributos y atributos booleanos

Los atributos añaden información o configuración a un elemento y se escriben en su etiqueta de apertura. `href` define el destino de un enlace, `class` asigna clases reutilizables, `id` identifica un elemento y atributos como `required` modifican el comportamiento de los controles de formulario. Los nombres y valores permitidos dependen del elemento y de la definición del atributo.

```html
<a href="/about" class="nav-link">About</a>
<button disabled>Save</button>
<input required>
```

Los atributos booleanos funcionan por presencia: si `disabled` aparece, el control está deshabilitado; si `required` aparece, el campo es obligatorio. Escribir `disabled="false"` sigue significando deshabilitado porque el atributo existe. Usa comillas de forma consistente en los valores normales, especialmente cuando pueden contener espacios o puntuación.
