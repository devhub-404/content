# Suspense and Lazy Loading

`lazy` defers loading a component module until it is first rendered. A Suspense boundary provides fallback UI while a child is suspended, whether from lazy code or from a framework/data source integrated with React's Suspense model.

```jsx
const Settings = lazy(() => import('./Settings.jsx'));

function App() {
  return (
    <Suspense fallback={<p>Loading settings…</p>}>
      <Settings />
    </Suspense>
  );
}
```

Suspense is a rendering coordination mechanism, not a universal data-fetching API by itself. Place boundaries around meaningful UI regions so one slow area does not blank the entire page. Nested boundaries can reveal content progressively as independent work becomes ready.
