# Layout Responsivo Antes de Breakpoints

CSS responsivo começa com fluxo flexível e restrições, não com uma lista de larguras de dispositivos. Deixe blocos usarem o espaço disponível, imagens permanecerem no container, texto quebrar, Flexbox quebrar linhas quando apropriado, Grid criar tracks intrínsecas e limites min/max manterem o conteúdo em tamanhos úteis.

```css
.page {
  inline-size: min(72rem, calc(100% - 2rem));
  margin-inline: auto;
}

img {
  max-inline-size: 100%;
  block-size: auto;
}
```

Adicione uma regra condicional quando o design precisar de mudança discreta, como passar de uma coluna para duas. Escolha o limite pelo conteúdo: redimensione até o arranjo atual ficar apertado ou até o espaço extra criar uma oportunidade útil. Design responsivo também inclui zoom, fontes do usuário, orientação, método de entrada e conteúdo localizado longo, não apenas largura do viewport.
