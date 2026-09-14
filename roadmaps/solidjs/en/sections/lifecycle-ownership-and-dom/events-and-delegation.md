# Events and Event Delegation

Solid supports JSX event handlers with both delegated and native-listener behavior depending on the event and syntax. Delegation lets many elements share a document-level listener, while some events use direct listeners because delegation does not fit their browser behavior.

```tsx
function Button() {
  function handleClick(event) {
    console.log(event.currentTarget.name);
  }

  return <button name="save" onClick={handleClick}>Save</button>;
}
```

Handlers are ordinary functions and do not create reactive dependencies merely because they read a signal at click time. This is useful: the handler sees the current value when invoked without needing to rerun during state changes. Preserve native semantic elements and keyboard behavior.
