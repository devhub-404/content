# Shorthands e Resets

Propriedades shorthand definem várias longhands relacionadas de uma vez. `margin`, `padding`, `border`, `background`, `font`, `flex`, `grid`, `transition` e `animation` são exemplos comuns. Elas deixam a intenção concisa quando você está descrevendo o grupo inteiro.

```css
.card {
  margin: 1rem 2rem;
  border: 1px solid #ccc;
  background: white;
}
```

Uma shorthand também pode resetar longhands que você não mencionou explicitamente. Substituir `background-color` depois por uma shorthand `background` pode resetar imagem, posição, repetição e outras subpropriedades. Use shorthands deliberadamente e inspecione estilos computados quando uma longhand anterior parecer sumir. Palavras-chave globais como `initial`, `inherit`, `unset`, `revert` e `revert-layer` oferecem tipos diferentes de reset.
