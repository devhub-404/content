# Dynamic Components and Portals

`Dynamic` selects an element or component from a reactive value without manually writing a large branch. `Portal` renders content into another DOM location while keeping it inside Solid's reactive ownership tree. Both are structural tools for UI that cannot be expressed by one fixed element tree.

```tsx
<Dynamic component={currentView()} user={user()} />

<Portal mount={document.body}>
  <div class="modal">Settings</div>
</Portal>
```

Use Dynamic when the component identity is truly data-driven; ordinary conditionals are clearer for a small fixed set of states. Portals are useful for overlays but still need accessible focus, labeling, and dismissal behavior. DOM location and reactive ownership are separate concerns.
