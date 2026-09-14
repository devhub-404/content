# Keyframes, Easing e Movimento Reduzido

`@keyframes` define valores em pontos de uma timeline de animação. Propriedades de animation controlam nome, duração, timing function, delay, número de iterações, direção, fill mode e play state. Easing mapeia progresso temporal para progresso do valor: linear dá avanço constante, curvas Bézier criam aceleração/desaceleração e `steps()` cria mudanças discretas.

```css
@keyframes pulse {
  0%, 100% { scale: 1; }
  50% { scale: 1.04; }
}

.busy {
  animation: pulse 1.2s ease-in-out infinite;
}

@media (prefers-reduced-motion: reduce) {
  .busy { animation: none; }
}
```

Animação infinita deve comunicar algo útil em vez de exigir atenção continuamente. `prefers-reduced-motion` permite ao usuário pedir menos movimento não essencial. Uma versão reduzida pode manter feedback de cor ou opacidade removendo grandes deslocamentos, zoom ou repetição. Trate a preferência como requisito de design, não apenas switch de performance.
