# Popovers

El atributo global `popover` crea contenido oculto que se muestra en la top layer. Un botón con `popovertarget` puede controlarlo declarativamente. El modo `auto` soporta light dismiss y coordinación con otros popovers automáticos; `manual` deja apertura y cierre bajo control explícito.

```html
<button popovertarget="help">Help</button>

<div id="help" popover>
  <p>Your order number appears on the receipt.</p>
</div>
```

Popover describe comportamiento de presentación, no un rol semántico. Puede contener ayuda, navegación, controles u otra estructura significativa, por lo que la semántica del contenido debe elegirse aparte. Como algunas partes del sistema son relativamente nuevas, comprueba el baseline de navegadores para la característica exacta que necesitas.
