# Expressões Regulares

Expressões regulares descrevem padrões de texto. JavaScript suporta literals regex e constructor `RegExp`, flags, classes de caracteres, quantificadores, grupos de captura e nomeados, backreferences, lookarounds, comportamento Unicode e integração com métodos de busca e substituição de strings.

```js
const pattern = /^(?<user>[a-z0-9._-]+)@(?<host>[a-z0-9.-]+)$/i;
const match = pattern.exec("mina@example.com");

if (match) {
  console.log(match.groups.user);
}
```

Regex é excelente para padrões lexicais, extração, busca e reescrita, mas não é automaticamente o validador certo para uma linguagem ou domínio complexo inteiro. Entenda matching global/stateful e `lastIndex`, e teste Unicode além de ASCII quando o input é visível ao usuário. Legibilidade importa: divida validação complicada em etapas compreensíveis quando um único padrão ficar opaco.
