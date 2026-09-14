# Iterables and Iterators

An iterable provides `[Symbol.iterator]()` returning an iterator. An iterator exposes `next()`, which returns `{ value, done }`. `for...of`, array spread, destructuring, `Array.from()`, and Set/Map constructors consume this protocol, allowing custom structures to participate in ordinary language syntax.

```js
const range = {
  from: 1,
  to: 3,
  *[Symbol.iterator]() {
    for (let value = this.from; value <= this.to; value++) {
      yield value;
    }
  },
};

console.log([...range]);
```

An iterator is a stateful cursor, while an iterable is the object that can supply one. Some objects return a fresh iterator every time; others are their own iterator and can be consumed only once. This distinction explains why certain sequences can be traversed repeatedly while generator results normally cannot be replayed without creating another generator.
