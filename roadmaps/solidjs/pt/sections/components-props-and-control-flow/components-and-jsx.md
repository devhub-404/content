# Components e JSX

Solid component normalmente é function que roda uma vez para criar estrutura DOM reativa. Expressions JSX retornadas continuam reativas porque compiler conecta às values lidas. Components são boundaries de setup, não render functions repetidas.

```tsx
function Badge(props) {
  return <span class="badge">{props.label}</span>;
}

<Badge label="New" />
```

Mantenha setup síncrono salvo API async específica e use reactive primitives para valores mutáveis. Locals comuns são calculados uma vez quando component executa. Essa distinção é essencial ao traduzir código de frameworks com rerender.
