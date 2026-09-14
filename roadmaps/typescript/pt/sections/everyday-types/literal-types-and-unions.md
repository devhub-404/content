# Literal Types e Unions

Literal type representa um valor exato, como `"dark"` ou `200`. Union types combinam alternativas com `|`, permitindo que uma API descreva valores que legitimamente possuem várias formas. Literals com unions costumam ser melhores que `string` amplo quando o vocabulário permitido é conhecido.

```ts
type Theme = "light" | "dark" | "system";
type Id = string | number;

function setTheme(theme: Theme) {
  // ...
}
```

Operações em union precisam ser seguras para todos os membros até que o fluxo faça narrowing. Design com unions é central no TypeScript: em vez de tornar toda propriedade opcional em um objeto gigante, modele estados realmente diferentes como membros separados. Isso torna combinações inválidas mais difíceis de representar.
