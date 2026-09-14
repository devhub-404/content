# Choosing State Shape and Derived Data

Good state stores the minimum independent information needed to describe the UI. If a value can be calculated from props or state during render, usually calculate it instead of storing another synchronized copy. Avoid redundant and contradictory state.

```jsx
const [firstName, setFirstName] = useState('Ada');
const [lastName, setLastName] = useState('Lovelace');

const fullName = `${firstName} ${lastName}`;
```

Normalize relationships when several objects refer to the same entity, and avoid deeply nested state if updates become awkward. State design is often more important than a clever hook: a clear source of truth makes updates, debugging, serialization, and testing much easier.
