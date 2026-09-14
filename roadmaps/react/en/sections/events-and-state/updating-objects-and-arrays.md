# Updating Objects and Arrays in State

Objects and arrays stored in state should be treated as immutable snapshots. To change them, create a new object or array that reuses unchanged values and replaces the parts that changed. Spread syntax, `map`, `filter`, and other non-mutating transformations are common tools.

```jsx
const [user, setUser] = useState({ name: 'Mina', active: false });

function activate() {
  setUser(current => ({
    ...current,
    active: true
  }));
}
```

Immutability is not a moral rule; it is how React can reason about snapshots and identity efficiently. Deeply nested updates are a signal to reconsider state shape, use a reducer, or adopt a helper library when the domain genuinely requires complex immutable transformations.
