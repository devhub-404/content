# Events e Event Delegation

Solid suporta event handlers JSX com delegation ou native listeners conforme event/syntax. Delegation permite muitos elements compartilharem listener no document, enquanto alguns events precisam listener direto por comportamento do browser.

```tsx
function Button() {
  function handleClick(event) {
    console.log(event.currentTarget.name);
  }

  return <button name="save" onClick={handleClick}>Save</button>;
}
```

Handlers são functions comuns e não criam reactive dependency só por ler signal no click. Isso é útil: handler vê valor atual quando executa sem rerun por state changes. Preserve semantic elements e keyboard behavior nativo.
