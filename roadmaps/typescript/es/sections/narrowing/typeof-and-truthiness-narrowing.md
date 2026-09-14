# Narrowing con `typeof` y truthiness

TypeScript sigue el flujo de control para reducir un tipo amplio a otro más específico. Checks con `typeof` estrechan primitivos y comparaciones explícitas eliminan null o identifican literals. Los checks de truthiness también hacen narrowing.

```ts
function format(value: string | number | null) {
  if (value === null) return "none";

  if (typeof value === "number") {
    return value.toFixed(2);
  }

  return value.toUpperCase();
}
```

Truthiness puede excluir valores válidos como `0` o `""`. Escribe primero el check que represente la regla del dominio, por ejemplo `value !== undefined`, y deja que el narrowing siga esa lógica. El checker funciona mejor cuando el código JavaScript ya es claro.
