# React DevTools e Profiling

React DevTools mostra component tree, props, state, Hooks e profiling. Profiler API/DevTools ajudam a identificar quais subtrees renderizam, quanto commits levam e se otimização realmente muda trabalho medido.

```jsx
<Profiler id="SearchResults" onRender={onRender}>
  <SearchResults query={query} />
</Profiler>
```

Profile build optimized parecido com production. Development checks alteram timing. Comece pela lentidão percebida, encontre interação cara e otimize causa medida em vez de assumir que todo rerender é ruim.
