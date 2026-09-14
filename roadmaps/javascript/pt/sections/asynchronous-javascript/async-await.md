# `async` e `await`

Uma função `async` sempre retorna Promise. `await` pausa aquela execução async até que valor promise-like seja settled e então produz o valor fulfilled ou lança o motivo da rejection. Ele não bloqueia o runtime inteiro; outro trabalho agendado pode continuar enquanto a operação está pendente.

```js
async function loadDashboard() {
  const response = await fetch("/api/dashboard");

  if (!response.ok) {
    throw new Error(`HTTP ${response.status}`);
  }

  return response.json();
}
```

`try`/`catch` funciona naturalmente ao redor de awaits. Evite awaits sequenciais quando o trabalho é independente—comece as operações juntas e componha. `await` no topo está disponível em módulos, mas módulo que espera durante avaliação pode atrasar módulos dependentes. Async/await é sintaxe estruturada sobre semântica de Promise, não outro sistema de concorrência.
