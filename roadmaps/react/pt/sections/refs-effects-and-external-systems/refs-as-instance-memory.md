# Refs como Memória de Instância

Ref armazena valor mutável que sobrevive a renders sem causar outro render quando muda. Isso serve a handles imperativos como timer IDs, DOM nodes, valores anteriores não visuais e integration objects que React não precisa exibir.

```jsx
function Stopwatch() {
  const intervalRef = useRef(null);

  function start() {
    intervalRef.current = setInterval(() => {}, 1000);
  }

  function stop() {
    clearInterval(intervalRef.current);
  }

  return <button onClick={start}>Start</button>;
}
```

Não use refs para esconder informação que deveria dirigir UI. Se mudar o valor deve mudar output renderizado, state normalmente é correto. Ler/escrever refs arbitrariamente durante render quebra expectativa de pureza, salvo padrões de inicialização cuidadosamente controlados.
