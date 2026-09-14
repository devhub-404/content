# Context

Context pasa un valor por el component subtree sin atravesar todas las props intermedias. El value puede contener signals, stores, service objects u otras reactive APIs, sirviendo para theme, session o domain services.

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

Define context cerca del dominio owner y ofrece un helper consumer cuando faltar provider deba ser error. Evita un context global catch-all. Los reactive values dentro del context permiten a consumers suscribirse solo a las partes leídas.
