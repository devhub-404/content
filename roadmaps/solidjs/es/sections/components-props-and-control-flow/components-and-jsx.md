# Components y JSX

Un Solid component suele ser una function que se ejecuta una vez para crear estructura DOM reactiva. Las expressions JSX retornadas siguen reactivas porque el compiler las conecta a los values leídos. Los components son boundaries de setup, no render functions repetidas.

```tsx
function Badge(props) {
  return <span class="badge">{props.label}</span>;
}

<Badge label="New" />
```

Mantén setup síncrono salvo APIs async específicas y usa reactive primitives para valores cambiantes. Los locals normales se calculan una vez cuando el component se ejecuta. Esta distinción es esencial al trasladar código desde frameworks de rerender.
