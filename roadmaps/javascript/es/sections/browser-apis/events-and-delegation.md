# Eventos y delegación

`addEventListener()` registra handlers sin sobrescribir otros y admite opciones como `once`, `passive`, `capture` y `signal`. `event.target` es donde se originó el evento y `event.currentTarget` el objeto cuyo listener se está ejecutando.

```js
const controller = new AbortController();

list.addEventListener("click", event => {
  const button = event.target.closest("button[data-id]");
  if (!button) return;

  removeItem(button.dataset.id);
}, { signal: controller.signal });
```

Muchos eventos recorren fases de capture y bubble. La delegación aprovecha el bubbling para manejar muchos descendientes desde un ancestro estable, muy útil en listas dinámicas. `preventDefault()` cancela acciones nativas cancelables y `stopPropagation()` cambia el flujo del evento; no debe ser un parche genérico para conflictos de diseño.
