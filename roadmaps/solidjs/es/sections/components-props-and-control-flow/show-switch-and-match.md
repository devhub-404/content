# UI Condicional con `Show`, `Switch` y `Match`

Los control-flow components conservan fine-grained reactivity mientras montan/disponen UI según condiciones. `Show` maneja una condition y fallback; `Switch`/`Match` expresan el primer branch coincidente entre varias alternativas.

```tsx
<Show when={user()} fallback={<Login />}>
  {current => <Profile user={current()} />}
</Show>

<Switch>
  <Match when={status() === "loading"}>Loading…</Match>
  <Match when={status() === "error"}>Failed</Match>
</Switch>
```

Estas primitives son útiles cuando hacen más claros ownership/lifetime de los branches que expressions JSX crudas. La callback form de `Show` proporciona un accessor narrowed del valor truthy, evitando lecturas repetidas y mejorando TypeScript.
