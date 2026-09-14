# Callbacks e Funções de Ordem Superior

Funções são valores de primeira classe: podem ser armazenadas, passadas, retornadas e colocadas em estruturas de dados. Callback é uma função passada para outra operação invocar. Higher-order function recebe funções, retorna funções ou ambos. Métodos de array, promises, event listeners, middleware e composição usam esse modelo.

```js
function repeat(times, action) {
  for (let i = 0; i < times; i++) {
    action(i);
  }
}

repeat(3, index => console.log(index));
```

Um callback pode executar sincronamente, assincronamente, uma vez ou muitas conforme a API, então o contrato importa. Não presuma que passar função torna algo assíncrono. Mantenha estado capturado explícito; quando callbacks ficam profundamente aninhados, extraia passos nomeados ou use abstração melhor como composição de promises.
