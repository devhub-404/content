# DOM Refs

A Solid `ref` gives direct access to the DOM element created by JSX. Because the component setup runs before mount completion, `onMount` is a natural place for imperative work that requires the element to be connected, such as focus, measurement, or a third-party widget.

```tsx
function Search() {
  let input;

  onMount(() => input.focus());

  return <input ref={input} />;
}
```

Use direct DOM access for operations that are truly imperative; let Solid own ordinary attributes and reactive content. If a reusable component needs to expose behavior, consider a callback ref or a small imperative API instead of leaking all internal DOM details.
