# Accesibilidad y Semántica Nativa del DOM

Solid compila a elementos normales de la web platform, así que HTML semántico sigue siendo la base de accessibility. Usa buttons, links, labels, headings, landmarks y forms nativos antes de recrearlos con elements genéricos/ARIA.

```tsx
function Dialog(props) {
  return (
    <div role="dialog" aria-modal="true" aria-labelledby="dialog-title">
      <h2 id="dialog-title">{props.title}</h2>
      {props.children}
      <button onClick={props.onClose}>Close</button>
    </div>
  );
}
```

Los reactive updates pueden cambiar focus, announcements, hidden content y navigation sin reload. El component behavior debe considerar keyboard/assistive tech. Fine-grained rendering mejora performance, no accessibility automática.
