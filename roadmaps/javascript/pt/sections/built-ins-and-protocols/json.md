# JSON

JSON é um formato textual relacionado à sintaxe de object literals JavaScript, porém mais restrito. Suporta objetos, arrays, strings, numbers, booleans e null. Não representa diretamente undefined, BigInt, funções, symbols, Map, Set, Date como tipo distinto ou grafos cíclicos.

```js
const text = JSON.stringify({
  id: 42,
  active: true,
});

const value = JSON.parse(text);
```

`JSON.stringify()` serializa dados suportados e pode usar replacer; `JSON.parse()` faz parse do texto e pode usar reviver. Fazer parse de JSON cria dados, não JavaScript executável, mas valores externos ainda precisam de validação de schema e domínio. Dates normalmente viram strings na serialização e precisam ser interpretadas intencionalmente na leitura.
