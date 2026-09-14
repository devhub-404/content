# Loops e Statements de Iteração

`for` expõe inicialização, condição e atualização. `while` repete enquanto uma condição permanecer truthy, e `do...while` executa o corpo pelo menos uma vez. `for...of` itera valores de um iterable como array, string, Map, Set ou generator.

```js
for (let i = 0; i < 3; i++) {
  console.log(i);
}

for (const item of items) {
  console.log(item);
}

while (queue.length > 0) {
  process(queue.shift());
}
```

`for...in` itera chaves de propriedades enumeráveis e é voltado principalmente à enumeração de propriedades, não valores de arrays. `break` encerra loop e `continue` inicia a próxima iteração. Prefira métodos de coleção quando a operação é naturalmente `map`, `filter` ou busca; prefira loop quando o próprio controle—saídas antecipadas, retries, várias mudanças de estado—é central.
