# Equality and Comparison

`===` and `!==` compare without the broad coercion used by `==` and `!=`, so strict equality is the normal default. Objects compare by identity: two distinct object literals are not equal simply because their properties contain equivalent values.

```js
0 === false;          // false
0 == false;           // true
Object.is(NaN, NaN);  // true

const sameUser = a.id === b.id;
```

`Object.is()` is a related sameness operation that treats `NaN` as the same as itself and distinguishes positive and negative zero. Map and Set use another defined sameness relation. For domain objects, decide what equality means—reference identity, a stable ID, or structural data—and implement that meaning explicitly instead of expecting the language to infer it.
