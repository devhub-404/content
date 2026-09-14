# `await using` y Disposable Stacks

`await using` gestiona recursos cuyo cleanup asíncrono se define con `[Symbol.asyncDispose]()` y espera ese cleanup al salir del scope. Solo se usa donde `await` es válido y tanto adquisición como liberación pueden ser asíncronas.

```js
async function read(openFile) {
  await using file = await openFile();
  return file.read();
}

{
  using stack = new DisposableStack();
  stack.defer(() => console.log("cleanup"));
}
```

`DisposableStack` y `AsyncDisposableStack` agrupan varias acciones de cleanup y preservan orden inverso y reglas de error. El sistema es opt-in: declarar un recurso con `const` no lo vuelve disposable automáticamente. Las convenciones de ownership siguen siendo esenciales.
