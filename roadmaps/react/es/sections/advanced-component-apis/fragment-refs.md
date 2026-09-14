# Fragment Refs

React 19.3 estabiliza refs en `<Fragment>` explícito. Fragment ref proporciona un handle imperativo que representa un grupo de child DOM nodes sin añadir wrapper, permitiendo operations como events, observation, focus o measurement sobre el grupo.

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

Úsalo cuando el DOM deba quedar wrapper-free pero el grupo necesite tratamiento imperativo. Es un escape hatch avanzado, no un motivo para eliminar elementos semánticos que harían más clara la estructura o accessibility.
