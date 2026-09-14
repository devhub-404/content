# Creación y actualización de contenido DOM

La API DOM puede crear, insertar, mover, reemplazar y eliminar nodes. `createElement()` crea un elemento, `textContent` establece texto sin interpretarlo como markup y métodos como `append`, `before`, `replaceWith` y `remove` modifican el árbol.

```js
const item = document.createElement("li");
item.className = "todo";
item.textContent = userInput;

list.append(item);
```

Usa APIs de texto para input no confiable. `innerHTML` parsea markup deliberadamente y puede crear XSS si recibe strings no confiables. Para HTML dinámico, construye nodos o usa una estrategia de sanitización confiable en vez de intentar escapar todo manualmente.
