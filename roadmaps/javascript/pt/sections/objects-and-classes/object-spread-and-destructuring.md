# Object Spread e Destructuring

Object spread copia propriedades próprias enumeráveis para novo objeto na ordem, então propriedades posteriores sobrescrevem anteriores com mesma chave. É cópia rasa: objetos e arrays aninhados continuam referências compartilhadas. Shorthand permite `{ name }` significar `{ name: name }`.

```js
const user = { name: "Mina", role: "admin" };
const updated = { ...user, role: "editor" };

const {
  name: displayName,
  role = "guest",
} = updated;
```

Destructuring extrai propriedades para bindings e suporta renomear, defaults, padrões aninhados e rest properties. Default se aplica apenas quando o valor extraído é `undefined`, não quando é `null`, `false` ou outro falsy. Spread é conveniente para records de dados, mas não preserva completamente descriptors ou comportamento de prototype.
