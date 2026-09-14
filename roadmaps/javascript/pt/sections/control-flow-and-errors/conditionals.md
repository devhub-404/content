# Condicionais

`if`, `else if` e `else` ramificam conforme truthiness. O operador condicional `condition ? a : b` é útil quando uma expressão precisa escolher entre dois valores; ternários profundamente aninhados normalmente ficam mais difíceis de ler que branches comuns.

```js
if (score >= 90) {
  grade = "A";
} else if (score >= 80) {
  grade = "B";
} else {
  grade = "C";
}

const status = active ? "online" : "offline";
```

`switch` compara uma expressão com cases discretos usando igualdade estrita e é útil quando vários valores conhecidos escolhem caminhos diferentes. Cases continuam até `break`, `return` ou outra saída interromper, então fallthrough intencional deve ser óbvio. Escolha a estrutura que deixe as regras mais fáceis de inspecionar.
