# `any`, `unknown` y `never`

`any` desactiva gran parte de la comprobación y permite que operaciones inseguras se propaguen. Úsalo como escape hatch deliberado, no como solución por defecto. `unknown` también puede contener cualquier valor, pero obliga a hacer narrowing antes de operar con él.

```ts
function parse(value: string): unknown {
  return JSON.parse(value);
}

function fail(message: string): never {
  throw new Error(message);
}
```

`never` representa un valor que no puede existir, como una función que siempre lanza o una rama imposible después de narrowing exhaustivo. Piensa en `unknown` como «todavía no sé qué es» y en `never` como «aquí no puede haber ningún valor».
