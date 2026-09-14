# Portals

Portal renderiza React children em outro DOM container mantendo-os na mesma component tree. Context continua funcionando e events propagam segundo a React tree, mesmo que os nodes DOM estejam em outro lugar.

```jsx
function Modal({ children }) {
  return createPortal(
    <div role="dialog" aria-modal="true">{children}</div>,
    document.body
  );
}
```

São úteis para dialogs, overlays e tooltips que precisam escapar clipping/stacking contexts. Não resolvem accessibility automaticamente: dialogs ainda precisam focus management, labels, escape behavior e semântica adequada.
