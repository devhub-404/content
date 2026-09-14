# Expresiones regulares

Las expresiones regulares describen patrones de texto. JavaScript ofrece literals regex y `RegExp`, flags, clases de caracteres, cuantificadores, grupos capturantes y nombrados, lookarounds y comportamiento Unicode, además de integración con métodos de búsqueda y reemplazo de strings.

```js
const pattern = /^(?<user>[a-z0-9._-]+)@(?<host>[a-z0-9.-]+)$/i;
const match = pattern.exec("mina@example.com");

if (match) {
  console.log(match.groups.user);
}
```

Son excelentes para patrones léxicos, extracción y reescritura, pero no automáticamente para validar un lenguaje o dominio complejo. Entiende el matching global, `lastIndex` y Unicode. Cuando un patrón grande deja de ser comprensible, divide el problema en etapas más legibles.
