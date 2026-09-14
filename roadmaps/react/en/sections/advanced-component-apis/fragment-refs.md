# Fragment Refs

React 19.3 stabilizes refs on explicit `<Fragment>` elements. A Fragment ref provides an imperative handle representing the group of child DOM nodes without adding a wrapper element, enabling operations such as event management, observation, focus, or measurement across the group.

```jsx
function Toolbar() {
  const fragmentRef = useRef(null);

  return (
    <Fragment ref={fragmentRef}>
      <button>Cut</button>
      <button>Copy</button>
      <button>Paste</button>
    </Fragment>
  );
}
```

Use Fragment refs when the DOM must remain wrapper-free but the group itself needs imperative treatment. They are an advanced escape hatch, not a reason to replace semantic wrapper elements that would make the document structure clearer or provide accessibility meaning.
