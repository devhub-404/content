# Exhaustiveness with `never`

After every member of a union has been eliminated by control flow, the remaining type is `never`. Assigning an allegedly unreachable value to `never` is a common way to make a switch exhaustive at compile time.

```ts
type Action =
  | { type: "save" }
  | { type: "delete"; id: string };

function handle(action: Action) {
  switch (action.type) {
    case "save":
      return save();
    case "delete":
      return remove(action.id);
    default: {
      const exhaustive: never = action;
      return exhaustive;
    }
  }
}
```

When a new union member is added later, the default branch stops being impossible and the assignment produces an error, directing you to update the handler. This is especially useful for reducers, protocol messages, state machines, and commands where forgetting a new case would otherwise become a runtime behavior gap.
