# Dynamic Import e `await` no Topo

`import()` carrega módulo dinamicamente e retorna Promise com seu module namespace object. É útil para features opcionais, code splitting por rota, módulos escolhidos pelo ambiente ou código caro que não pertence ao caminho inicial.

```js
async function openEditor() {
  const { createEditor } = await import("./editor.js");
  return createEditor();
}

// module top level
const config = await loadConfig();
```

`await` no topo é permitido em módulos e torna avaliação do módulo assíncrona. Módulos dependentes esperam essa avaliação terminar, então espera excessiva no topo pode alongar o startup crítico. Use quando a prontidão realmente pertence à inicialização do módulo; caso contrário exporte função async para o consumidor escolher quando o trabalho começa.
