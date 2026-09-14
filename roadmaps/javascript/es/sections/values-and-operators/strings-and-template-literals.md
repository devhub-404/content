# Strings y template literals

Las strings son secuencias inmutables de code units UTF-16. Pueden escribirse con comillas simples, dobles o template literals. Los templates usan backticks, admiten varias líneas e interpolan expresiones con `${...}`. Los métodos de string devuelven nuevos valores en lugar de mutar la original.

```js
const first = "Ada";
const last = "Lovelace";
const label = `${first} ${last}`;

const message = `Hello,
${label}!`;
```

Indexación y `.length` trabajan con code units, por lo que algunos caracteres Unicode ocupan más de una unidad. `for...of` maneja mejor code points comunes, aunque un carácter visible puede contener varios code points. Para comparación, ordenación, segmentación o formato sensible a locale, usa `Intl`.
