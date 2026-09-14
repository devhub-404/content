# Inputs Controlados e Forms

Um field controlado recebe seu valor atual do React state e reporta edits por event handler. Isso cria uma source of truth quando outra UI depende do valor, validation precisa reagir imediatamente ou submit usa state atual do component.

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

Nem todo field precisa ser controlled. Forms nativos, `FormData`, refs e React form actions podem reduzir state quando cada keystroke não interessa. Preserve semântica HTML com labels, input types adequados, validation nativa quando útil e errors acessíveis.
