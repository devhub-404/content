# Refs as Instance Memory

A ref stores a mutable value that survives renders without causing another render when it changes. This is useful for imperative handles such as timer IDs, DOM nodes, previous non-visual values, and integration objects that React does not need to display.

```jsx
function Stopwatch() {
  const intervalRef = useRef(null);

  function start() {
    intervalRef.current = setInterval(() => {}, 1000);
  }

  function stop() {
    clearInterval(intervalRef.current);
  }

  return <button onClick={start}>Start</button>;
}
```

Do not use refs to hide information that should drive the UI. If changing a value should change rendered output, state is usually the right tool. Reading or writing arbitrary refs during render breaks the expectation that rendering is pure, except for carefully controlled initialization patterns.
