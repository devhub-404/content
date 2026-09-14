# Reactive State Fora de Components

Signals podem existir em modules fora de components, facilitando shared state. Module-level state tem lifetime da instância do module e pode servir a estado realmente global no client ou internals de library.

```tsx
const [session, setSession] = createSignal(null);

export function currentSession() {
  return session();
}

export function login(user) {
  setSession(user);
}
```

Global reactivity aumenta coupling e pode quebrar isolamento entre requests em SSR. Prefira context/per-request roots quando cada tree/request precisa state independente. Module state deve ser escolha deliberada de lifetime, não default para toda feature.
