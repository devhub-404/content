# Recursão

Recursão significa uma função chamar a si mesma direta ou indiretamente. Algoritmos recursivos corretos precisam de caso-base que interrompa novas chamadas e passo recursivo que avance em direção a ele. Árvores, estruturas aninhadas, parsers e algoritmos divide-and-conquer frequentemente possuem forma naturalmente recursiva.

```js
function factorial(n) {
  if (n <= 1) return 1;
  return n * factorial(n - 1);
}
```

Chamadas recursivas comuns consomem espaço da call stack, e engines JavaScript práticos não otimizam tail calls universalmente, então recursão muito profunda pode estourar a stack. Use iteração ou stack explícita quando a profundidade pode ser grande ou controlada por entrada não confiável. Escolha recursão quando ela torna estrutura ou algoritmo mais compreensível.
