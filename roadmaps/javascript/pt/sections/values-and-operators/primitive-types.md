# Tipos Primitivos

JavaScript possui sete tipos primitivos: string, number, bigint, boolean, undefined, symbol e o valor especial null. Todo o resto é objeto. Valores primitivos são imutáveis, mesmo que uma variável que os contém possa receber outro valor depois.

```js
const name = "Mina";       // string
const count = 42;          // number
const exact = 42n;         // bigint
const active = true;       // boolean
const missing = undefined;
const empty = null;
const key = Symbol("key");
```

`typeof` é útil, mas possui peculiaridades históricas: `typeof null` é `"object"`, e arrays também retornam `"object"`. Use `Array.isArray()` para arrays e checks explícitos para null quando necessário. Symbols são identificadores primitivos únicos usados em property keys e protocolos da linguagem. BigInt lida com inteiros arbitrariamente grandes, mas não mistura diretamente com aritmética Number.
