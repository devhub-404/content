# Event Handlers

Event handlers run because the user or browser triggered an interaction, so they are the natural place for side effects caused by that interaction. React passes event objects to handlers and uses camelCase event props such as `onClick` and `onChange`.

```jsx
function SaveButton({ onSave }) {
  function handleClick(event) {
    event.preventDefault();
    onSave();
  }

  return <button onClick={handleClick}>Save</button>;
}
```

Pass a function to an event prop instead of calling it during render. Keep event logic near the interaction it handles, and move reusable business logic into ordinary functions. Event propagation follows DOM concepts, including bubbling and explicit `stopPropagation` when truly necessary.
