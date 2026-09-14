# Optional, Readonly, and Index Signatures

A property marked `?` may be absent. A `readonly` property cannot be assigned through that typed reference after initialization, although readonly is a compile-time restriction and does not deep-freeze runtime objects. Index signatures describe families of property names whose exact keys are not known ahead of time.

```ts
interface Settings {
  readonly id: string;
  theme?: "light" | "dark";
  [key: `plugin:${string}`]: unknown;
}
```

Optional does not always mean the same thing as “present with value `undefined`,” especially with stricter optional-property settings. Index signatures should describe a real dynamic-key domain; avoid using `[key: string]: any` to silence errors on an object whose fields are actually known. Prefer explicit properties plus a narrow index pattern when possible.
