# Igualdade e Comparação

`===` e `!==` comparam sem a coerção ampla usada por `==` e `!=`, então igualdade estrita é o padrão normal. Objetos comparam por identidade: dois object literals distintos não são iguais apenas porque suas propriedades possuem valores equivalentes.

```js
0 === false;          // false
0 == false;           // true
Object.is(NaN, NaN);  // true

const sameUser = a.id === b.id;
```

`Object.is()` é uma operação relacionada que considera `NaN` igual a si mesmo e diferencia zero positivo de negativo. Map e Set usam outra relação definida de igualdade. Para objetos de domínio, decida o que igualdade significa—identidade de referência, ID estável ou dados estruturais—e implemente isso explicitamente em vez de esperar que a linguagem deduza.
