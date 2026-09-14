# Discriminated Unions

A discriminated union gives each member a shared property whose literal value identifies that member. Checking the discriminant narrows the entire object, so fields that belong only to one state become available without casts.

```ts
type Result =
  | { status: "ok"; value: string }
  | { status: "error"; error: Error };

function show(result: Result) {
  if (result.status === "ok") {
    return result.value;
  }

  return result.error.message;
}
```

This is one of TypeScript's strongest modeling patterns for UI states, protocol messages, command results, and domain workflows. It avoids impossible combinations such as `{ loading: true, data: ..., error: ... }` when those states should be mutually exclusive. Model states as separate valid shapes rather than one bag of optional properties.
