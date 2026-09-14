# State como Snapshot

State permite que un component recuerde información entre renders. Cada render recibe un snapshot de los valores de state de ese momento; llamar un setter solicita otro render en vez de cambiar la variable ya capturada por el handler actual.

```jsx
function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      Count: {count}
    </button>
  );
}
```

Este modelo explica por qué un log justo después del setter suele mostrar el valor anterior. Guarda solo información que deba persistir. Las variables locales normales se recrean en cada render y son mejores para cálculos derivados sin memoria propia.
