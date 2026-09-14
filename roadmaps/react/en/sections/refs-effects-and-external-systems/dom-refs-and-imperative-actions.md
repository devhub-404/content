# DOM Refs and Imperative Actions

React normally manages DOM creation and updates, but a DOM ref gives controlled imperative access when an operation is inherently imperative: focus, selection, measuring, scrolling, media playback, or connecting a third-party widget.

```jsx
function Search() {
  const inputRef = useRef(null);

  return (
    <>
      <input ref={inputRef} />
      <button onClick={() => inputRef.current?.focus()}>
        Focus
      </button>
    </>
  );
}
```

Avoid using refs to manually change DOM that React also owns, because a later render may overwrite or conflict with those changes. Expose narrow imperative methods from reusable components rather than leaking their entire internal DOM structure to parents.
