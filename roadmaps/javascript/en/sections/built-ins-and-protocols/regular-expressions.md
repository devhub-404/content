# Regular Expressions

Regular expressions describe text patterns. JavaScript supports regex literals and the `RegExp` constructor, flags, character classes, quantifiers, capturing and named groups, backreferences, lookarounds, Unicode-aware behavior, and integration with string search and replacement methods.

```js
const pattern = /^(?<user>[a-z0-9._-]+)@(?<host>[a-z0-9.-]+)$/i;
const match = pattern.exec("mina@example.com");

if (match) {
  console.log(match.groups.user);
}
```

Regex is excellent for lexical patterns, extraction, search, and rewriting, but not automatically the right validator for an entire complex language or business domain. Understand global/stateful matching and `lastIndex`, and test Unicode text beyond ASCII when the input is user-visible. Readability matters: split complicated validation into understandable stages when a single pattern becomes opaque.
