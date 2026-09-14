# Decorators Padrão

TypeScript moderno suporta o modelo padronizado de decorators introduzido no TypeScript 5.0. Decorator recebe valor decorado e objeto de contexto e pode observar, substituir ou inicializar elementos de classe suportados conforme a semântica da proposta.

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

Esse modelo é diferente do sistema experimental antigo de decorators e suas convenções de metadata. Bibliotecas precisam dizer qual modelo exigem. Decorators são metaprogramação poderosa e podem esconder fluxo de controle, então use quando framework ou abstração transversal realmente se beneficia da indireção.
