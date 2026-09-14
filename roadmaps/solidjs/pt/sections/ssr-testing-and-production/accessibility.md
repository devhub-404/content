# Acessibilidade e Semântica Nativa do DOM

Solid compila para elementos comuns da web platform, então HTML semântico continua base de accessibility. Use buttons, links, labels, headings, landmarks e forms nativos antes de recriá-los com elements genéricos/ARIA.

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

Reactive updates podem mudar focus, announcements, hidden content e navigation sem reload. Component behavior precisa considerar keyboard/assistive tech. Fine-grained rendering melhora performance, não accessibility automática.
