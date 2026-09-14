# Refs como Memoria de Instancia

Una ref almacena un valor mutable que sobrevive a renders sin causar otro render cuando cambia. Sirve para handles imperativos como timer IDs, DOM nodes, valores anteriores no visuales e integration objects que React no necesita mostrar.

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

No uses refs para ocultar información que debería dirigir la UI. Si cambiar el valor debe cambiar el output renderizado, state suele ser correcto. Leer/escribir refs arbitrariamente durante render rompe la expectativa de pureza, salvo patrones de inicialización cuidadosamente controlados.
