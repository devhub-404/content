# Effects

`createEffect` ejecuta side-effecting code en respuesta a reactive dependencies. Rastrea signals y otros valores leídos durante la ejecución y vuelve a correr cuando cambian. Los Effects sirven para sincronizar con el mundo externo, no para derived values normales.

```tsx
const [theme, setTheme] = createSignal("dark");

createEffect(() => {
  document.documentElement.dataset.theme = theme();
});
```

Prefiere memos o expresiones reactivas directas para computation. Dentro del effect, mantén la acción externa enfocada y combina subscriptions/resources con `onCleanup`. Un effect que solo escribe otro signal suele indicar una relación de state que puede modelarse de forma más directa.
