# Context

Context passa valor pela component subtree sem atravessar todas as props intermediárias. O value pode conter signals, stores, service objects ou outras reactive APIs, servindo a theme, session ou domain services.

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

Defina context perto do domínio owner e forneça helper consumer quando provider ausente deve ser erro. Evite context global catch-all. Reactive values dentro do context permitem consumers assinar apenas partes lidas.
