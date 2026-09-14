# Media Queries e Sintaxe de Range

`@media` aplica regras condicionalmente com base em features como largura/altura do viewport, orientação, resolução, display mode, capacidade de cor e preferências do usuário. Sintaxe moderna de comparação expressa ranges diretamente e pode ser mais clara que formas antigas `min-*`/`max-*`.

```css
@media (width >= 48rem) {
  .layout {
    display: grid;
    grid-template-columns: 1fr 18rem;
  }
}

@media (40rem <= width < 70rem) {
  .toolbar { gap: .5rem; }
}
```

Mantenha o layout mais simples fora da query quando isso cria baseline robusto e aprimore em condições onde outro arranjo se torna útil. Não crie breakpoint para toda pequena diferença visual. Se uma regra realmente depende do tamanho de um componente reutilizável e não do viewport, use container query.
