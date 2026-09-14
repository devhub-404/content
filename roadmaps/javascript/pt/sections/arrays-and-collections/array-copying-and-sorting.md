# Copiando e Ordenando Arrays

Os métodos tradicionais `sort()`, `reverse()` e `splice()` mutam o array. As contrapartes de cópia `toSorted()`, `toReversed()`, `toSpliced()` e `with()` retornam array atualizado preservando o original. Esse estilo é útil quando dados são compartilhados ou transições de estado precisam ser fáceis de comparar.

```js
const sorted = users.toSorted((a, b) =>
  a.name.localeCompare(b.name)
);

const reversed = items.toReversed();
const updated = items.with(1, "new value");
const removed = items.toSpliced(2, 1);
```

A ordenação padrão compara formas string, então arrays numéricos precisam de comparator como `(a, b) => a - b`. Ordenação de texto sensível a locale normalmente deve usar `localeCompare()` ou `Intl.Collator`. Métodos de cópia são rasos: elementos objeto no novo array ainda referenciam os mesmos objetos, salvo se também forem copiados.
