# Array Destructuring e Spread

Array destructuring lê valores de um iterable por posição e pode pular valores, fornecer defaults, aninhar padrões ou coletar o restante. Spread expande iterable em array literal, lista de argumentos ou outra sintaxe suportada. Os dois recursos funcionam com iterables, não apenas arrays reais.

```js
const [first, second, ...rest] = items;
const copy = [...items];
const combined = [...left, ...right];

function point([x, y]) {
  return { x, y };
}
```

`[...array]` faz cópia rasa, então identidade de objetos aninhados continua compartilhada. Espalhar iterable enorme em argumentos de função pode atingir limites do runtime. Destructuring de parâmetros é conciso para inputs tuple-like pequenos e fixos, mas padrões aninhados complexos podem esconder a forma esperada do caller.
