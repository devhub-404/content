# Eventos e Delegação

`addEventListener()` adiciona handlers sem sobrescrever outros listeners e suporta opções como `once`, `passive`, `capture` e `signal`. `event.target` é onde o evento originou; `event.currentTarget` é o objeto cujo listener está executando.

```js
const controller = new AbortController();

list.addEventListener("click", event => {
  const button = event.target.closest("button[data-id]");
  if (!button) return;

  removeItem(button.dataset.id);
}, { signal: controller.signal });
```

Muitos eventos viajam pelas fases capture e bubble. Event delegation usa bubbling para tratar várias interações descendentes a partir de ancestral estável e é especialmente útil para listas dinâmicas. `preventDefault()` cancela ação padrão cancelável do navegador; `stopPropagation()` altera propagação e não deve ser usado como forma genérica de esconder conflitos de design de eventos.
