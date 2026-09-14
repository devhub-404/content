# Mutation and State Updates

Objects and arrays are mutable references. Mutation is not inherently wrong, but shared mutable state creates hidden coupling because several parts of a program can observe and change the same object. Copy-on-write updates are useful when a system benefits from clear before/after values, as in many UI architectures.

```js
const nextUser = {
  ...user,
  settings: {
    ...user.settings,
    theme: "dark",
  },
};
```

Spread and array copying methods are shallow, so nested references need their own copy when they also change. Do not deep-clone everything mechanically; cloning changes identity and is expensive or incorrect for class instances, Maps, functions, host objects, and external resources. Choose mutation or copying based on ownership and observation rules.
