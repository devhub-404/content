# Box Model e `box-sizing`

Uma caixa CSS possui áreas de conteúdo, padding, borda e margem. Com o padrão `content-box`, largura ou altura declarada descreve o content box, então padding e bordas aumentam o tamanho externo. `border-box` faz o tamanho declarado incluir padding e borda e é um baseline comum porque o sizing de componentes fica mais previsível.

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

.card {
  inline-size: 20rem;
  padding: 1rem;
  border: 1px solid #ccc;
  margin-block: 1rem;
}
```

Padding cria espaço dentro da borda; margin cria espaço fora. Backgrounds pintam áreas específicas da caixa enquanto margens ficam transparentes. Use a visualização de box model do DevTools quando o tamanho surpreender. Muitos problemas de “por que isso ficou maior que 300px?” são apenas confusão sobre qual borda da caixa o valor descreve.
