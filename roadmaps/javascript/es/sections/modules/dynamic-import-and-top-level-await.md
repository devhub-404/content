# Dynamic import y `await` en el nivel superior

`import()` carga un módulo dinámicamente y devuelve una Promise con su namespace. Es útil para features opcionales, code splitting, módulos elegidos por entorno o código costoso que no pertenece al camino inicial.

```js
async function openEditor() {
  const { createEditor } = await import("./editor.js");
  return createEditor();
}

// module top level
const config = await loadConfig();
```

Top-level `await` hace asíncrona la evaluación de un módulo y sus dependientes esperan a que termine. Úsalo cuando esa espera sea realmente parte de la preparación del módulo; si no, una función async exportada deja al consumidor decidir cuándo empieza el trabajo.
