# Dynamic Import and Top-level `await`

`import()` loads a module dynamically and returns a Promise for its module namespace object. It is useful for optional features, route-level code splitting, environment-selected modules, or expensive code that does not belong on the initial path.

```js
async function openEditor() {
  const { createEditor } = await import("./editor.js");
  return createEditor();
}

// module top level
const config = await loadConfig();
```

Top-level `await` is allowed in modules and makes module evaluation asynchronous. Dependent modules wait for that evaluation to complete, so excessive top-level waiting can lengthen the critical startup path. Use it when readiness genuinely belongs to module initialization; otherwise export an async function so consumers choose when the work begins.
