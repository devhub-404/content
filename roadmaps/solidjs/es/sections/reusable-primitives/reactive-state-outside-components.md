# Reactive State Fuera de Components

Los signals pueden existir en modules fuera de components, facilitando shared state. El module-level state tiene el lifetime de la instancia del module y puede servir para estado realmente global en client o internals de una library.

```tsx
const [session, setSession] = createSignal(null);

export function currentSession() {
  return session();
}

export function login(user) {
  setSession(user);
}
```

La reactividad global aumenta coupling y puede romper aislamiento entre requests en SSR. Prefiere context/per-request roots cuando cada tree/request necesite state independiente. El module state debe ser una elección deliberada de lifetime, no el default para cada feature.
