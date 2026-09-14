# Transitions with `useTransition`

A Transition marks non-urgent state updates that may take longer to render. Urgent interactions such as typing can update immediately while React works on the transition in the background, and `isPending` lets the UI communicate that lower-priority work is still progressing.

```jsx
function SearchPage() {
  const [query, setQuery] = useState('');
  const [filter, setFilter] = useState('');
  const [isPending, startTransition] = useTransition();

  function update(value) {
    setQuery(value);
    startTransition(() => setFilter(value));
  }
}
```

Transitions do not make slow JavaScript faster and are not a debounce timer. They change update priority and allow interruptible rendering. Keep immediate input state separate from expensive derived UI when responsiveness matters, and profile the actual bottleneck if rendering remains slow.
