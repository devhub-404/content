# Controlled Inputs and Forms

A controlled form field receives its current value from React state and reports edits through an event handler. This gives one source of truth when other UI depends on the same value, validation must react immediately, or submitting should use the current component state.

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

Not every field must be controlled. Native forms, `FormData`, refs, and React form actions can reduce state when intermediate keystrokes are not meaningful to the application. Preserve HTML semantics: use labels, correct input types, native validation where useful, and accessible error messages.
