# Decorators estándar

TypeScript moderno soporta el modelo estandarizado de decorators introducido en TypeScript 5.0. Un decorator recibe el valor decorado y un context object y puede observar, reemplazar o inicializar determinados elementos de clase.

```ts
function logged(
  original: (this: any, ...args: any[]) => any,
  context: ClassMethodDecoratorContext
) {
  return function (this: any, ...args: any[]) {
    console.log(`calling ${String(context.name)}`);
    return original.call(this, ...args);
  };
}

class Service {
  @logged
  run() {}
}
```

Este sistema es distinto del modelo experimental antiguo y sus convenciones de metadata. Una biblioteca debe indicar cuál espera. Los decorators añaden metaprogramación e indirección, por lo que conviene usarlos cuando un framework o una abstracción transversal aporta suficiente valor.
