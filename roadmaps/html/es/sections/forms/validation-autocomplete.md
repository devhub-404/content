# Validación y autocomplete

HTML puede expresar restricciones comunes con `required`, `minlength`, `maxlength`, `min`, `max`, `step` y `pattern`. El navegador puede impedir el envío nativo si un control no cumple esas reglas y exponer estados de validez a CSS y JavaScript.

```html
<input
  name="username"
  required
  minlength="3"
  maxlength="20"
  pattern="[A-Za-z0-9_]+"
  autocomplete="username">
```

`autocomplete` indica qué dato real representa un campo mediante tokens como `name`, `email`, `username`, `current-password`, `street-address` y `postal-code`. Un buen autocomplete reduce escritura y ayuda a gestores de contraseñas. Las restricciones del cliente mejoran la interacción, pero no son una frontera de seguridad: valida nuevamente en el servidor.
