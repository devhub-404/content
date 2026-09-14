# Dynamic Components y Portals

`Dynamic` selecciona element/component desde un valor reactivo sin un gran branch manual. `Portal` renderiza contenido en otra ubicación DOM manteniéndolo en el reactive ownership tree de Solid. Ambos ayudan cuando la estructura no cabe en un tree fijo.

```tsx
<Dynamic component={currentView()} user={user()} />

<Portal mount={document.body}>
  <div class="modal">Settings</div>
</Portal>
```

Usa Dynamic cuando component identity sea realmente data-driven; conditionals normales son más claros para pocos states fijos. Los Portals ayudan con overlays, pero aún requieren focus, labels y dismissal accesibles. DOM location y ownership son concerns distintos.
