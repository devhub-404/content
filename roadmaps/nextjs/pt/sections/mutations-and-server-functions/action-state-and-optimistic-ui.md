# Action State e Optimistic UI

Client Components podem usar `useActionState`, `useFormStatus` e `useOptimistic` com Server Actions para mostrar pending, validation results ou optimistic changes enquanto server operation termina.

```tsx
"use client";

const [state, action, pending] = useActionState(saveProfile, { error: null });
const [optimisticName, setOptimisticName] = useOptimistic(name);
```

Mantenha server response autoritativa. Optimistic UI deve ser reversível e não declarar sucesso security-sensitive cedo. Modele validation errors como data do form; falhas inesperadas vão para logging/error boundary/fallback seguro.
