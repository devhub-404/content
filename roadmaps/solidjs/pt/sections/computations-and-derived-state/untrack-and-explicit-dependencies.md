# `untrack`, `on` e Controle Explícito de Dependencies

Solid normalmente descobre dependencies automaticamente, mas `on` pode fazer computation reagir a sources explícitas e `untrack` lê valor reativo sem assinar o tracking scope atual. São ferramentas precisas de dependency control.

```tsx
createEffect(on(userId, id => {
  const themeNow = untrack(theme);
  console.log("user changed", id, themeNow);
}));
```

Não use para silenciar reatividade não compreendida. Se valor realmente afeta o resultado, normalmente deve ser dependency. `untrack` serve a leitura incidental como logging/contexto pontual; `on` quando a própria boundary é parte do design.
