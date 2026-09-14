# Numbers, BigInt e Math

Number usa ponto flutuante IEEE-754 de dupla precisão. Inteiros são exatos apenas dentro do safe-integer range, e muitas frações decimais não podem ser representadas exatamente em binário. `Number` oferece helpers de conversão e validação, enquanto `Math` fornece funções e constantes numéricas comuns.

```js
const average = (10 + 15 + 20) / 3;
const rounded = Math.round(average);
const safe = Number.isFinite(rounded);

const huge = 9_007_199_254_740_993n;
```

Valores BigInt usam sufixo `n` e representam inteiros sem o limite de inteiro seguro de Number. Aritmética BigInt exige operandos BigInt e divisão inteira trunca. BigInt serve para inteiros realmente grandes, não cálculos financeiros decimais comuns. Código financeiro normalmente usa unidades menores inteiras ou solução decimal em vez de pressupor ponto flutuante binário exato.
