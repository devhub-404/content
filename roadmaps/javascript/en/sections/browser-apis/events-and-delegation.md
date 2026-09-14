# Events and Delegation

`addEventListener()` attaches event handlers without overwriting other listeners and supports options such as `once`, `passive`, `capture`, and `signal`. `event.target` is where the event originated; `event.currentTarget` is the object whose listener is currently running.

```js
const controller = new AbortController();

list.addEventListener("click", event => {
  const button = event.target.closest("button[data-id]");
  if (!button) return;

  removeItem(button.dataset.id);
}, { signal: controller.signal });
```

Many events travel through capture and bubble phases. Event delegation uses bubbling to handle many descendant interactions from a stable ancestor and is especially useful for dynamic lists. `preventDefault()` cancels a cancelable default browser action; `stopPropagation()` changes propagation and should not be used as a generic way to hide event-design conflicts.
