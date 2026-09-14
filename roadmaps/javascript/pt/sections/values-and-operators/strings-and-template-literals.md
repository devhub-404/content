# Strings e Template Literals

Strings são sequências imutáveis de code units UTF-16. Podem ser escritas com aspas simples, duplas ou template literals. Templates usam crase, podem ocupar várias linhas e interpolam expressões com `${...}`. Métodos de string retornam novos valores em vez de alterar a string original.

```js
const first = "Ada";
const last = "Lovelace";
const label = `${first} ${last}`;

const message = `Hello,
${label}!`;
```

Indexação e `.length` trabalham em code units UTF-16, então alguns caracteres Unicode ocupam mais de uma unidade. `for...of` lida melhor com code points Unicode comuns que indexação, mas um grapheme visível ainda pode conter vários code points. Use `Intl` para comparação, ordenação, segmentação e formatação sensíveis a locale em vez de pressupor texto semelhante a ASCII.
