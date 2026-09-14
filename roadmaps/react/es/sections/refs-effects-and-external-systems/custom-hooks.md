# Custom Hooks y Lógica Stateful Reutilizable

Un custom Hook empaqueta lógica React reutilizable conservando el component que posee el state. Los nombres empiezan con `use` y pueden llamar otros Hooks según las Rules of Hooks. Son excelentes para subscriptions, reducers, integración con browser y comportamiento de dominio.

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

Los custom Hooks comparten lógica, no una única instancia de state. Cada llamada recibe su propio state salvo conexión con external store/context. Diseña el retorno según la necesidad del caller en vez de exponer cada setter y detalle interno.
