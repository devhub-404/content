# Type Predicates and Assertion Functions

A user-defined type guard returns a type predicate such as `value is User`, allowing a reusable runtime test to narrow callers' variables. An assertion function with `asserts value is User` tells the checker that successful return guarantees the asserted type.

```ts
function isUser(value: unknown): value is User {
  return (
    typeof value === "object" &&
    value !== null &&
    "id" in value &&
    "name" in value
  );
}

function assertUser(value: unknown): asserts value is User {
  if (!isUser(value)) throw new Error("Invalid user");
}
```

The annotation must accurately describe the runtime test. TypeScript trusts your predicate body more than it can verify it, so an incorrect guard creates unsoundness. For complex external data, schema validators that derive or integrate with types are safer than hand-writing incomplete property checks across the codebase.
