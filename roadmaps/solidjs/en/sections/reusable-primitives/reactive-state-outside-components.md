# Reactive State Outside Components

Signals can exist in modules outside components, which makes shared state easy to create. Module-level state has application-wide lifetime for that module instance and can be useful for truly global client state or library internals.

```tsx
const [session, setSession] = createSignal(null);

export function currentSession() {
  return session();
}

export function login(user) {
  setSession(user);
}
```

Global reactivity is convenient but increases coupling and complicates server request isolation when code is reused in SSR. Prefer context or per-request roots when each application tree or request should have independent state. Shared module state should be a deliberate lifetime choice, not the default for every feature.
