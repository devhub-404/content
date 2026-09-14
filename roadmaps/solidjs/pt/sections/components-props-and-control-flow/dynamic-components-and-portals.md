# Dynamic Components e Portals

`Dynamic` seleciona element/component de valor reativo sem grande branch manual. `Portal` renderiza conteúdo em outro local DOM mantendo-o na reactive ownership tree do Solid. Ambos ajudam estruturas que não cabem em tree fixa.

```tsx
<Dynamic component={currentView()} user={user()} />

<Portal mount={document.body}>
  <div class="modal">Settings</div>
</Portal>
```

Use Dynamic quando component identity é realmente data-driven; conditionals comuns são mais claros para poucos states fixos. Portals ajudam overlays, mas ainda exigem focus, labels e dismissal acessíveis. DOM location e ownership são concerns diferentes.
