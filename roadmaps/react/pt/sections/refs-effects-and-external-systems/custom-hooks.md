# Custom Hooks e Lógica Stateful Reutilizável

Custom Hook empacota lógica React reutilizável preservando o component que possui o state. Nomes começam com `use` e podem chamar outros Hooks conforme Rules of Hooks. São ótimos para subscriptions, reducers, browser integration e comportamento de domínio.

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

Custom Hooks compartilham lógica, não uma única instância de state. Cada chamada recebe state próprio salvo conexão com external store/context. Projete retorno conforme necessidade do caller em vez de expor todo setter e detalhe interno.
