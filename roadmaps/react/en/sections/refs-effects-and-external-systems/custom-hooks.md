# Custom Hooks and Reusable Stateful Logic

A custom Hook packages reusable React logic while preserving the component that owns the state. Hook names start with `use` and may call other Hooks according to the Rules of Hooks. They are excellent for subscriptions, reusable reducers, browser integrations, and domain-specific state behavior.

```jsx
function useOnlineStatus() {
  const [online, setOnline] = useState(navigator.onLine);

  useEffect(() => {
    const update = () => setOnline(navigator.onLine);
    window.addEventListener('online', update);
    window.addEventListener('offline', update);
    return () => {
      window.removeEventListener('online', update);
      window.removeEventListener('offline', update);
    };
  }, []);

  return online;
}
```

Custom Hooks share logic, not one state instance. Each call gets its own React state unless the Hook connects to shared external state or context. Design the returned API around the caller's needs instead of exposing every internal setter and implementation detail.
