# Funções e Valores de Retorno

Funções são objetos chamáveis. Uma function declaration cria binding nomeado inicializado durante a preparação do escopo; uma function expression cria função como expressão e pode ser armazenada onde qualquer valor pode. Chamar função cria seu próprio contexto local de execução.

```js
function add(a, b) {
  return a + b;
}

const multiply = function (a, b) {
  return a * b;
};
```

`return` encerra a invocação atual e fornece resultado. Chegar ao fim sem expressão retornada produz `undefined`. Funções nomeadas melhoram stack traces e recursão. Prefira funções com entradas, saídas e efeitos colaterais claros, mas não divida operação simples em helpers cujos nomes não acrescentam informação.
