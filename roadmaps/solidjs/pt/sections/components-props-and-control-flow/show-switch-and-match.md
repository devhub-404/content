# UI Condicional com `Show`, `Switch` e `Match`

Control-flow components preservam fine-grained reactivity enquanto montam/dispose UI conforme condições. `Show` trata uma condition e fallback; `Switch`/`Match` expressam primeiro branch correspondente entre alternativas.

```tsx
<Show when={user()} fallback={<Login />}>
  {current => <Profile user={current()} />}
</Show>

<Switch>
  <Match when={status() === "loading"}>Loading…</Match>
  <Match when={status() === "error"}>Failed</Match>
</Switch>
```

Essas primitives são úteis quando deixam ownership/lifetime dos branches mais claros que expressions JSX cruas. Callback form de `Show` fornece accessor narrowed do valor truthy, evitando reads repetidos e melhorando TypeScript.
