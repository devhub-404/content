# React DevTools and Profiling

React DevTools shows the component tree, props, state, Hooks, and profiling information. The Profiler API and DevTools profiler help identify which subtrees render, how long commits take, and whether an optimization actually changes measured work.

```jsx
<Profiler id="SearchResults" onRender={onRender}>
  <SearchResults query={query} />
</Profiler>
```

Profile a production-like optimized build when investigating real performance. Development checks and source maps change timing. Start from user-visible slowness, find the expensive interaction, and optimize the measured cause rather than assuming every rerender is harmful.
