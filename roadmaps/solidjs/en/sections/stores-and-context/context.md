# Context

Context passes a value through a component subtree without threading it through every intermediate prop. The context value can itself contain signals, stores, service objects, or other reactive APIs, making it suitable for cross-cutting dependencies such as theme, session, or domain services.

```tsx
const ThemeContext = createContext("light");

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Page />
    </ThemeContext.Provider>
  );
}

const theme = useContext(ThemeContext);
```

Define context near the domain that owns it and provide a custom consumer helper when missing providers should be an error. Avoid one catch-all global context. Fine-grained reactive values inside a context let consumers subscribe only to the pieces they actually read.
