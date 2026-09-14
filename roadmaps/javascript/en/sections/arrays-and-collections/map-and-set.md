# `Map` and `Set`

`Map` is a keyed collection whose keys can be values of any type, including objects, and whose iteration preserves insertion order. `Set` stores unique values. Both provide `has`, `delete`, `clear`, iteration, and a `size` property; Map additionally provides `set` and `get`.

```js
const visits = new Map();
visits.set(user, 3);

const tags = new Set(["js", "web", "js"]);
tags.add("css");

console.log(tags.size);
```

Use objects for record-like data with known property names and Map when keys themselves are dynamic data. Use Set for membership and uniqueness rather than repeatedly searching an array. Map and Set use SameValueZero equality: `NaN` can match itself, while object keys still compare by identity.
