# Narrowing com `typeof` e Truthiness

TypeScript acompanha o fluxo para estreitar tipo amplo em tipo mais específico. Checks com `typeof` fazem narrowing de categorias primitivas, enquanto igualdade explícita pode remover null ou combinar literals. Checks de truthiness também estreitam, mas podem excluir valores falsy válidos como `0` ou string vazia.

```ts
function format(value: string | number | null) {
  if (value === null) return "none";

  if (typeof value === "number") {
    return value.toFixed(2);
  }

  return value.toUpperCase();
}
```

Escreva checks de runtime que reflitam primeiro a regra de domínio; o narrowing deve surgir naturalmente. Se `0` é válido, verifique `value !== undefined` em vez de `if (value)`. Bom código TypeScript raramente precisa informar manualmente fatos que fluxo JavaScript comum já consegue provar.
