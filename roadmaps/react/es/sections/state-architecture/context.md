# Context para Valores Transversales

Context permite leer un valor profundamente en el component tree sin pasar la misma prop por cada intermediario. Funciona bien para theme, locale, información del authenticated user o un service object compartido por un subtree.

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

Context es dependency injection, no un state manager automático. Cambios frecuentes del provider pueden afectar muchos consumers y un context enorme crea coupling amplio. Sepáralos por responsabilidad y mantén props cuando la relación parent-child es directa.
