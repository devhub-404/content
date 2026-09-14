# Objetos e Propriedades

Objetos são coleções mutáveis de propriedades cujas chaves são strings ou symbols. Object literals os criam de forma concisa, e computed property syntax pode usar expressão como chave. Dot notation funciona para nomes semelhantes a identificadores; bracket notation é necessária para chaves dinâmicas e nomes incomuns.

```js
const field = "email";

const user = {
  id: 42,
  name: "Mina",
  [field]: "mina@example.com",
};

console.log(user.name);
console.log(user["email"]);
```

Ler propriedade ausente normalmente produz `undefined` depois da busca no prototype. Assignment cria ou atualiza propriedades, e `delete` remove propriedades próprias configuráveis. Use `Object.hasOwn()` quando precisar distinguir propriedade própria de herdada pela prototype chain. Objetos funcionam bem como records estruturados; Maps costumam ser melhores quando as próprias chaves são dados dinâmicos.
