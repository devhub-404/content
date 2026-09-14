# Context para Valores Transversais

Context permite ler um valor profundamente na component tree sem passar a mesma prop por todo intermediário. Funciona bem para theme, locale, informações do authenticated user ou service object compartilhado por uma subtree.

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

Context é dependency injection, não state manager automático. Mudanças frequentes no provider podem afetar muitos consumers e um context gigante cria coupling amplo. Separe por responsabilidade e mantenha props quando a relação parent-child é direta.
