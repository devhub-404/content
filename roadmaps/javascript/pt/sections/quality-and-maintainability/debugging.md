# Depurando JavaScript

Debuggers modernos podem pausar execução, inspecionar escopos léxicos, avaliar expressões, avançar chamadas, observar valores, inspecionar rede e preservar informação de stack async. Breakpoints normalmente informam mais que muitos logs temporários porque permitem examinar o estado exato antes de ele mudar.

```js
function calculateTotal(items) {
  debugger;
  return items.reduce((sum, item) => sum + item.price, 0);
}
```

Reproduza o bug com o menor caso confiável, identifique o primeiro ponto onde o estado observado diverge do esperado e retroceda. Use console para diagnóstico direcionado, não tratamento de erros da aplicação. Quando código é bundled ou transpilado, source maps permitem que o debugger aponte para os módulos escritos originalmente.
