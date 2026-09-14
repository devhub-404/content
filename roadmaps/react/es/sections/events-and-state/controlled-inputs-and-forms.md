# Inputs Controlados y Forms

Un field controlado recibe su valor actual del React state y reporta edits mediante un event handler. Esto crea una source of truth cuando otra UI depende del valor, la validation debe reaccionar inmediatamente o el submit usa el state actual del component.

```jsx
function SearchBox() {
  const [query, setQuery] = useState('');

  return (
    <label>
      Search
      <input value={query} onChange={e => setQuery(e.target.value)} />
    </label>
  );
}
```

No todo field debe ser controlled. Forms nativos, `FormData`, refs y React form actions pueden reducir state cuando cada keystroke no importa. Conserva semántica HTML con labels, input types correctos, validation nativa cuando sirva y errores accesibles.
