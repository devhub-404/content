# Portals

Un portal renderiza React children en otro DOM container manteniéndolos en el mismo component tree. Context sigue funcionando y los events se propagan según el React tree, aunque los nodes DOM estén en otro lugar.

```jsx
function Modal({ children }) {
  return createPortal(
    <div role="dialog" aria-modal="true">{children}</div>,
    document.body
  );
}
```

Son útiles para dialogs, overlays y tooltips que deben escapar clipping/stacking contexts. No resuelven accessibility automáticamente: los dialogs aún necesitan focus management, labels, escape behavior y semántica adecuada.
