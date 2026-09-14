# Program Invariants and Validation

An invariant is a condition that must remain true for later code to be meaningful. JavaScript has no dedicated application assertion statement, so ordinary checks and errors are often the clearest way to enforce public preconditions or impossible internal states.

```js
function transfer(amount) {
  if (!Number.isFinite(amount) || amount <= 0) {
    throw new RangeError("amount must be a positive finite number");
  }

  // Later code can rely on the invariant.
}
```

Validate untrusted or external data at system boundaries, then allow inner code to rely on the validated shape. Diagnostic APIs such as `console.assert()` are not a dependable validation contract. A useful failure happens close to the violated assumption and provides enough context for the caller or developer to take action.
