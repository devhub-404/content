# Writing Modes e Propriedades Lógicas

CSS descreve layout em eixos lógicos para suportar escrita da esquerda para direita, direita para esquerda e vertical. O eixo inline segue a progressão do texto; o eixo block segue o empilhamento de linhas e blocos. `writing-mode` pode mudar esses eixos, enquanto a direção do documento normalmente deve vir da informação semântica de direção do HTML.

```css
.card {
  inline-size: min(100%, 40rem);
  padding-block: 1rem;
  padding-inline: 1.25rem;
}

.badge {
  inset-block-start: .5rem;
  inset-inline-end: .5rem;
}
```

Propriedades lógicas expressam geometria relativa ao fluxo: `inline-size`/`block-size`, `margin-inline`, `padding-block` e insets lógicos. Elas reduzem overrides específicos de direção e tornam componentes mais portáveis. Use propriedades físicas como `top` ou `left` quando a relação for realmente física, não apenas porque o design inicial era left-to-right.
