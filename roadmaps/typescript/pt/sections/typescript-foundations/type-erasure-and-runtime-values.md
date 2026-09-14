# Type Erasure e Valores de Runtime

Type aliases, interfaces, argumentos genéricos e a maior parte da sintaxe de tipos não existem em runtime. Eles orientam checker e editor e depois desaparecem do JavaScript emitido. Em geral não é possível perguntar em runtime se um objeto “implementa uma interface” porque essa interface foi apagada.

```ts
type UserId = string;

interface User {
  id: UserId;
  name: string;
}

const user: User = { id: "u1", name: "Mina" };
console.log(user.name);
```

Validação de runtime precisa de dados de runtime: `typeof`, `instanceof`, checks de propriedades, schemas, parsers ou bibliotecas de validação. Classes e enums podem criar valores de runtime, enquanto interfaces e type aliases não. Mantenha clara a distinção entre mundo de tipos e mundo de valores ao projetar APIs ou depurar JavaScript emitido.
