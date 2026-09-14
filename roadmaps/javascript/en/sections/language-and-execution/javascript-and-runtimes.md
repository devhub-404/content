# JavaScript and Runtimes

JavaScript is the programming language standardized as ECMAScript. The language specification defines its syntax, values, objects, functions, promises, modules, and built-in objects. A runtime surrounds that language with host APIs. Browsers provide the DOM, events, Fetch, storage, timers, and other Web APIs; server runtimes provide a different environment.

```js
const total = 2 + 3;
console.log(total);
```

That distinction is fundamental. `Array`, `Map`, `Promise`, and `JSON` belong to JavaScript itself, while `document`, `fetch`, and `localStorage` belong to the browser platform. The same language can run in different hosts even though the globals and I/O facilities change. Learn the language model first, then the APIs of the environment where your program runs.
