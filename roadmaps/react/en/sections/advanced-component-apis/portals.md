# Portals

A portal renders React children into a different DOM container while they remain part of the same React component tree. Context still works and events propagate according to the React tree, even though the actual DOM nodes live elsewhere.

```jsx
function Modal({ children }) {
  return createPortal(
    <div role="dialog" aria-modal="true">{children}</div>,
    document.body
  );
}
```

Portals are useful for dialogs, overlays, tooltips, and UI that must escape clipping or stacking contexts. They do not solve accessibility automatically: dialogs still need focus management, labels, escape behavior, and appropriate semantic attributes.
