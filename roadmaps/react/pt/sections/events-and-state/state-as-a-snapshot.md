# State como Snapshot

State permite que um component lembre informação entre renders. Cada render recebe um snapshot dos valores de state daquele momento; chamar setter solicita outro render em vez de mudar a variável já capturada pelo handler atual.

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

Esse modelo explica por que log logo após setter costuma mostrar valor anterior. Armazene apenas informação que precisa persistir. Variáveis locais comuns são recriadas a cada render e servem melhor a cálculos derivados sem memória própria.
