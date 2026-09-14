# Tipando Parâmetros `this`

TypeScript pode declarar parâmetro fictício inicial chamado `this` para descrever o receiver esperado por função comum. O parâmetro é apagado e não muda a convenção de chamada em runtime; apenas verifica que a função é invocada com receiver compatível.

```ts
interface User {
  name: string;
}

function greet(this: User, message: string) {
  return `${message}, ${this.name}`;
}

const user = { name: "Mina", greet };
user.greet("Hello");
```

Isso é útil para bibliotecas de callbacks e métodos que dependem de `this` dinâmico do JavaScript. Arrow functions não podem declarar esse parâmetro porque seu `this` é léxico. Se API não precisa realmente de semântica de receiver, argumentos explícitos normalmente são mais fáceis de compor e testar.
