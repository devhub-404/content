# Deferred Values

`useDeferredValue` gives a value a lagging version that can update at lower priority. It is useful when a parent already owns the urgent state but a slow child should keep showing the previous result briefly while a new render is prepared.

```jsx
function Results({ query }) {
  const deferredQuery = useDeferredValue(query);
  const stale = query !== deferredQuery;

  return <SearchResults query={deferredQuery} dimmed={stale} />;
}
```

Deferred values do not delay network requests by themselves and do not provide a fixed time delay. They defer rendering work. Use them when preserving the old UI is preferable to blocking input or immediately replacing useful content with a loading state.
