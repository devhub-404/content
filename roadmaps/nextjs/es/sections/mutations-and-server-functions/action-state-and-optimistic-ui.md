# Action State y Optimistic UI

Los Client Components pueden usar `useActionState`, `useFormStatus` y `useOptimistic` con Server Actions para mostrar pending, validation results u optimistic changes mientras termina la server operation.

```tsx
"use client";

const [state, action, pending] = useActionState(saveProfile, { error: null });
const [optimisticName, setOptimisticName] = useOptimistic(name);
```

Mantén la server response como autoridad. Optimistic UI debe ser reversible y no declarar éxito security-sensitive demasiado pronto. Modela validation errors como data del form; fallos inesperados van a logging/error boundary/fallback seguro.
