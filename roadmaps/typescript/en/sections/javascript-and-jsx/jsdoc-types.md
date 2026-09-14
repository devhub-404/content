# TypeScript Types in JSDoc

Checked JavaScript can express rich types with JSDoc, including parameters, returns, object shapes, generics, imports, overload-like declarations, and `@satisfies`. This is useful for libraries that want to remain JavaScript source or for gradual migrations.

```ts
/**
 * @template T
 * @param {T[]} items
 * @returns {T | undefined}
 */
export function first(items) {
  return items[0];
}
```

JSDoc typing and `.ts` syntax use the same checker but have different authoring ergonomics and a few feature differences. Do not duplicate the implementation's obvious types in huge comments; annotate the contracts inference cannot recover, especially public functions and external-data boundaries.
