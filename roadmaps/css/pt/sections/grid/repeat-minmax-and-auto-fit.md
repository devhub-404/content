# `repeat()`, `minmax()` e Grids com Auto-fit

`repeat()` remove sintaxe repetida de tracks, enquanto `minmax()` fornece limites inferior e superior. Com `auto-fit` ou `auto-fill`, Grid pode criar quantas tracks couberem no espaço. Isso frequentemente produz layouts responsivos de cards sem breakpoint de viewport.

```css
.cards {
  display: grid;
  grid-template-columns:
    repeat(auto-fit, minmax(min(16rem, 100%), 1fr));
  gap: 1rem;
}
```

`auto-fit` colapsa tracks repetidas vazias para as existentes se expandirem; `auto-fill` mantém os slots de track. O minimum `min(16rem, 100%)` evita overflow quando o container inteiro é menor que o minimum nominal do card. Use esse padrão intrínseco quando o requisito é simplesmente “encaixe quantas colunas utilizáveis o espaço permitir”.
