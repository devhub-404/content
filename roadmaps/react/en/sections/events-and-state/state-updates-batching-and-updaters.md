# State Updates, Batching, and Updater Functions

React batches related state updates before rendering so an event does not cause unnecessary intermediate renders. When the next state depends on the previous state, pass an updater function; React queues those functions and applies them in order to the latest pending value.

```jsx
function Counter() {
  const [count, setCount] = useState(0);

  function addThree() {
    setCount(c => c + 1);
    setCount(c => c + 1);
    setCount(c => c + 1);
  }

  return <button onClick={addThree}>{count}</button>;
}
```

Do not mutate an existing state object or array and then pass the same reference back. Create the next value from the previous one. Updater functions are especially important when several updates may happen before React commits the next render.
