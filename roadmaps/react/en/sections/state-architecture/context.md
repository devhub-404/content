# Context for Cross-cutting Values

Context lets a value be read deep in a component tree without threading the same prop through every intermediate component. It works well for concerns such as theme, locale, authenticated user information, or a service object shared by one subtree.

```jsx
const ThemeContext = createContext('light');

function App() {
  return (
    <ThemeContext value="dark">
      <Toolbar />
    </ThemeContext>
  );
}

function Button() {
  const theme = useContext(ThemeContext);
  return <button className={theme}>Save</button>;
}
```

Context is dependency injection, not an automatic state-management system. Frequent provider-value changes can affect many consumers, and using one huge context can create broad coupling. Split contexts by responsibility and keep ordinary props when the relationship between parent and child is direct.
