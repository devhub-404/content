# DOM Querying and Traversal

The DOM is a browser-provided object model for the document. `querySelector()` and `querySelectorAll()` use CSS selectors to locate elements, while the node tree exposes parent, child, and sibling relationships. Query from the narrowest stable root you already have rather than repeatedly searching the entire document.

```js
const form = document.querySelector("#signup");
const fields = form.querySelectorAll("input");

for (const field of fields) {
  console.log(field.name);
}

console.log(form.parentElement);
```

`querySelectorAll()` returns a static NodeList; some older DOM APIs return live collections that change as the document changes. Prefer direct references and semantic structure over selectors that depend on many accidental wrappers. The DOM is a host API, so none of these objects exist in a plain ECMAScript environment unless the runtime supplies an equivalent.
