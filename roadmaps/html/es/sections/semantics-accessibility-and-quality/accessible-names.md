# Nombres accesibles

Los controles interactivos y el contenido embebido necesitan nombres que indiquen qué son. Distintos elementos obtienen su nombre de maneras nativas diferentes: formularios desde `label`, imágenes desde `alt`, botones desde su texto e iframes desde `title`. El texto visible suele ser el mejor punto de partida porque ayuda a todo el mundo.

```html
<label for="search">Search products</label>
<input id="search" name="q" type="search">

<img src="warning.svg" alt="Warning: high voltage">

<iframe src="/chart" title="Quarterly revenue chart"></iframe>
```

No añadas `aria-label` por reflejo cuando el contenido visible ya proporciona el nombre correcto. El cálculo del nombre accesible tiene reglas de precedencia y un label ARIA puede reemplazar texto visible en el árbol de accesibilidad. Usa ARIA cuando los mecanismos nativos no basten y comprueba el nombre resultante con herramientas de accesibilidad.
