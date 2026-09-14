# `async` y `await`

Una función `async` siempre devuelve una Promise. `await` pausa esa ejecución async hasta que el valor promise-like se resuelve y produce su fulfillment o lanza su rejection. No bloquea todo el runtime: otro trabajo agendado puede continuar.

```js
async function loadDashboard() {
  const response = await fetch("/api/dashboard");

  if (!response.ok) {
    throw new Error(`HTTP ${response.status}`);
  }

  return response.json();
}
```

`try`/`catch` funciona de forma natural alrededor de awaits. No serialices operaciones independientes por costumbre; inícialas y compónlas. `await` en el nivel superior existe en módulos, pero puede retrasar la evaluación de dependientes. Async/await es sintaxis estructurada sobre Promises, no otro modelo de concurrencia.
