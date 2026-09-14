# Tipos TypeScript em JSDoc

JavaScript verificado pode expressar tipos ricos com JSDoc, incluindo parâmetros, retornos, object shapes, generics, imports, declarations parecidas com overload e `@satisfies`. Isso é útil para bibliotecas que querem manter source JavaScript ou migrações graduais.

```ts
/**
 * @template T
 * @param {T[]} items
 * @returns {T | undefined}
 */
export function first(items) {
  return items[0];
}
```

Tipagem JSDoc e sintaxe `.ts` usam o mesmo checker mas possuem ergonomia diferente e algumas diferenças de recursos. Não duplique em comentários enormes tipos óbvios da implementação; anote contratos que a inferência não recupera, especialmente funções públicas e fronteiras de dados externos.
