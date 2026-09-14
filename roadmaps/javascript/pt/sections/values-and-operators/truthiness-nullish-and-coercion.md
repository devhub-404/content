# Truthiness, Valores Nullish e Coerção

Condições convertem valores para boolean. Os valores falsy são `false`, `0`, `-0`, `0n`, `NaN`, string vazia, `null` e `undefined`; quase todo o resto, inclusive arrays e objetos vazios, é truthy. Valores nullish são especificamente apenas `null` e `undefined`.

```js
const input = "";
if (!input) {
  console.log("No input");
}

const page = settings.page ?? 1;
const count = Number("42");
```

`??` usa fallback apenas para valores nullish, diferente de `||`, que usa fallback para qualquer falsy. Isso importa quando `0`, `false` ou `""` são significativos. JavaScript também faz coerção implícita em vários operadores, especialmente `+`. Prefira `Number()`, `String()` ou `Boolean()` explícitos em fronteiras quando a conversão esperada não estiver clara.
