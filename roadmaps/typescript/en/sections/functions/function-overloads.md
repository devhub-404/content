# Function Overloads

Overload signatures describe several supported call shapes followed by one implementation signature. Callers see the overloads, while the implementation must be compatible with them. Overloads are useful when return type or valid parameters change in ways that depend on call shape.

```ts
function parse(value: string): string[];
function parse(value: Uint8Array): string[];
function parse(value: string | Uint8Array): string[] {
  const text =
    typeof value === "string"
      ? value
      : new TextDecoder().decode(value);

  return text.split(",");
}
```

Prefer union parameters or generics when they describe the relationship more directly. Many overloads that differ only slightly are harder to maintain and can infer poorly for callers holding union values. The implementation signature is not an additional public overload, so document the actual supported call forms in the overload list.
