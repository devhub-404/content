# Bordas, Radius, Outlines e Shadows

Bordas ocupam espaço da caixa; border radius arredonda bordas e cantos do background. Cantos arredondados não cortam automaticamente descendentes que vazam, a menos que o overflow também faça clipping. Box shadows são efeitos pintados fora ou dentro da caixa e não mudam o tamanho de layout.

```css
.card {
  border: 1px solid rgb(0 0 0 / .15);
  border-radius: 1rem;
  box-shadow: 0 .75rem 2rem rgb(0 0 0 / .18);
}

.card :focus-visible {
  outline: 3px solid Highlight;
  outline-offset: 3px;
}
```

Outlines são desenhadas sem ocupar espaço e são especialmente úteis para indicadores de foco. Não remova outlines globalmente. Shadows e bordas sutis podem apoiar hierarquia visual, mas limites e estados importantes devem continuar compreensíveis em high contrast ou forced colors, onde a pintura do autor pode ser alterada.
