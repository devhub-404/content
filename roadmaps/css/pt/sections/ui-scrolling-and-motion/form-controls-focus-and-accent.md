# Controles de Formulário, Foco e Accent Color

Controles nativos de formulário possuem estilização do navegador e da plataforma. Comece herdando tipografia e alterando espaçamento, bordas, cores e `accent-color` antes de remover a aparência nativa. `appearance: none` transfere mais responsabilidade ao seu CSS e deve ser usado apenas quando o produto realmente precisa de rendering personalizado.

```css
input,
button,
select,
textarea {
  font: inherit;
}

input[type="checkbox"],
input[type="radio"] {
  accent-color: #2457d6;
}

:focus-visible {
  outline: 3px solid Highlight;
  outline-offset: 3px;
}
```

Indicação de foco é essencial para navegação por teclado. `:focus-visible` permite ao navegador mostrar seu estilo de foco quando um sinal visível é apropriado. Mantenha alvos de toque grandes, permita que labels e validação quebrem linha e teste zoom, forced colors, teclado e touch. Estilo deve aprimorar semântica nativa, não esconder o controle e reconstruí-lo mal.
