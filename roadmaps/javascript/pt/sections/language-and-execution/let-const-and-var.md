# `let`, `const` e `var`

Use `const` quando o próprio binding não será reatribuído e `let` quando reatribuição fizer parte do algoritmo. Ambos possuem escopo de bloco e ficam em temporal dead zone até a inicialização. `const` não torna um objeto imutável; apenas impede atribuir outro valor àquele binding.

```js
const taxRate = 0.2;
let total = 100;
total += total * taxRate;

if (total > 100) {
  const message = "Large total";
  console.log(message);
}
```

`var` possui escopo de função, é inicializado como `undefined` durante hoisting e pode ser redeclarado no mesmo escopo. Código existente ainda contém `var`, então é importante entender o comportamento, mas código novo normalmente fica mais claro com `const` e `let`. Declare valores perto do início de sua vida útil em vez de criar grandes escopos mutáveis.
