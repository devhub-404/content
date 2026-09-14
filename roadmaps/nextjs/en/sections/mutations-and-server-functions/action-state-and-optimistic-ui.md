# Action State and Optimistic UI

Client Components can use React action hooks such as `useActionState`, `useFormStatus`, and `useOptimistic` around Server Actions to show pending state, validation results, or immediate optimistic changes while the authoritative server operation completes.

```tsx
"use client";

const [state, action, pending] = useActionState(saveProfile, { error: null });
const [optimisticName, setOptimisticName] = useOptimistic(name);
```

Keep the server response authoritative. Optimistic UI should be reversible and should not claim security-sensitive success before the server confirms it. Model expected validation errors as data the form can display, while unexpected failures belong to logging and an error boundary or safe fallback.
