# Event Handlers

Event handlers executam porque usuário ou navegador iniciou uma interação, então são o lugar natural para side effects causados por essa interação. React passa event objects e usa props camelCase como `onClick` e `onChange`.

```jsx
function SaveButton({ onSave }) {
  function handleClick(event) {
    event.preventDefault();
    onSave();
  }

  return <button onClick={handleClick}>Save</button>;
}
```

Passe uma function para o event prop em vez de chamá-la durante render. Mantenha lógica perto da interação e mova business logic reutilizável para funções comuns. Propagation segue conceitos do DOM, incluindo bubbling e `stopPropagation` quando necessário.
