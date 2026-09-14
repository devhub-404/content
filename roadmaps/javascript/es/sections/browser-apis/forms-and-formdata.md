# Formularios y `FormData`

HTML ya proporciona submission, labels, controles y constraint validation. JavaScript puede escuchar `submit`, inspeccionar controles, llamar `checkValidity()`/`reportValidity()` y crear un `FormData` con los campos exitosos del formulario.

```js
form.addEventListener("submit", event => {
  if (!form.checkValidity()) {
    event.preventDefault();
    form.reportValidity();
    return;
  }

  const data = new FormData(form);
  console.log(data.get("email"));
});
```

Escucha el submit del formulario, no solo el click del botón, para conservar teclado y otros caminos nativos. La validación cliente es feedback, no seguridad; el servidor debe validar otra vez. `FormData` también puede enviarse directamente por Fetch para datos multipart.
