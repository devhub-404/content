# Accessibility and Native DOM Semantics

Solid compiles to ordinary web platform elements, so semantic HTML remains the accessibility foundation. Use native buttons, links, labels, headings, landmarks, and form behavior before recreating them with generic elements and ARIA.

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

Reactive updates can change focus, announcements, hidden content, and navigation without page reloads, so component behavior must account for keyboard and assistive-technology users. Fine-grained rendering improves performance but does not automatically make a custom interaction accessible.
