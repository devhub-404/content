# Fragment Refs

React 19.3 estabiliza refs em `<Fragment>` explícito. Fragment ref fornece handle imperativo representando grupo de child DOM nodes sem adicionar wrapper, permitindo operações como events, observation, focus ou measurement sobre o grupo.

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

Use quando o DOM precisa ficar wrapper-free mas o grupo precisa tratamento imperativo. É escape hatch avançado, não motivo para remover elementos semânticos que deixariam document structure ou accessibility mais claros.
