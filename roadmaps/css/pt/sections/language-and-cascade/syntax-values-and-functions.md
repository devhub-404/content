# Declarações, Valores, Funções e At-rules

Uma declaração é uma propriedade seguida de um valor. Valores podem ser palavras-chave, números, dimensões, porcentagens, cores, URLs, imagens, funções ou combinações definidas pela gramática daquela propriedade. Funções como `min()`, `calc()`, `rgb()` e `var()` fazem parte da sintaxe de valores; não são chamadas JavaScript.

```css
@media (width >= 48rem) {
  .card {
    width: min(40rem, 100%);
    color: rgb(20 30 50 / 0.9);
  }
}
```

At-rules começam com `@` e introduzem comportamento maior que uma única declaração. Algumas envolvem regras, como `@media`, `@supports`, `@container`, `@layer` e `@scope`; outras definem recursos ou timelines, como `@font-face` e `@keyframes`. CSS é tolerante a erros: uma declaração desconhecida ou inválida normalmente é ignorada enquanto o CSS válido ao redor continua.
