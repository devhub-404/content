# Copying and Sorting Arrays

Traditional `sort()`, `reverse()`, and `splice()` mutate their array. The copying counterparts `toSorted()`, `toReversed()`, `toSpliced()`, and `with()` return an updated array while preserving the original. This style is useful when data is shared or state transitions should remain easy to compare.

```js
const sorted = users.toSorted((a, b) =>
  a.name.localeCompare(b.name)
);

const reversed = items.toReversed();
const updated = items.with(1, "new value");
const removed = items.toSpliced(2, 1);
```

Default sorting compares string forms, so numeric arrays need a comparator such as `(a, b) => a - b`. Locale-sensitive text sorting should normally use `localeCompare()` or `Intl.Collator`. Copying methods are shallow: object elements in the new array are still references to the same objects unless you also copy those objects.
