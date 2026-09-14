# Event Handlers

Los event handlers se ejecutan porque el usuario o navegador inició una interacción, por lo que son el lugar natural para side effects causados por esa interacción. React pasa event objects y usa props camelCase como `onClick` y `onChange`.

```jsx
function SaveButton({ onSave }) {
  function handleClick(event) {
    event.preventDefault();
    onSave();
  }

  return <button onClick={handleClick}>Save</button>;
}
```

Pasa una function al event prop en vez de llamarla durante render. Mantén la lógica cerca de la interacción y mueve business logic reutilizable a funciones normales. La propagation sigue conceptos del DOM, incluido bubbling y `stopPropagation` cuando sea necesario.
