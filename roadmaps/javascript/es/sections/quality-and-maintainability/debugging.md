# Depuración de JavaScript

Los debuggers modernos permiten pausar ejecución, inspeccionar scopes, evaluar expresiones, avanzar por llamadas, observar valores, revisar red y conservar stacks asíncronas. Un breakpoint suele informar más que añadir muchos logs temporales porque muestra el estado exacto antes de cambiar.

```js
function calculateTotal(items) {
  debugger;
  return items.reduce((sum, item) => sum + item.price, 0);
}
```

Reproduce el bug con el caso fiable más pequeño, encuentra el primer punto donde el estado real diverge del esperado y trabaja hacia atrás. Usa la consola para diagnóstico, no como estrategia de error handling. Si hay bundling o transpilation, los source maps conectan el código ejecutado con los módulos originales.
