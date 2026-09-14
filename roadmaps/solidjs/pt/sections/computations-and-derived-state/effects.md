# Effects

`createEffect` roda side-effecting code em resposta a reactive dependencies. Ele rastreia signals e outros valores lidos durante execução e roda novamente quando mudam. Effects servem para sincronizar com mundo externo, não para derived values comuns.

```tsx
const [theme, setTheme] = createSignal("dark");

createEffect(() => {
  document.documentElement.dataset.theme = theme();
});
```

Prefira memos ou expressões reativas diretas para computation. Dentro de effect, mantenha ação externa focada e combine subscriptions/resources com `onCleanup`. Effect que só escreve outro signal muitas vezes indica relação de state que pode ser modelada diretamente.
