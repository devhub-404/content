# React DevTools y Profiling

React DevTools muestra component tree, props, state, Hooks y profiling. La Profiler API/DevTools ayudan a identificar qué subtrees renderizan, cuánto duran los commits y si una optimización realmente cambia el trabajo medido.

```jsx
<Profiler id="SearchResults" onRender={onRender}>
  <SearchResults query={query} />
</Profiler>
```

Perfila un build optimizado parecido a production. Los development checks cambian timing. Empieza por lentitud visible, encuentra la interacción costosa y optimiza la causa medida en vez de asumir que todo rerender es malo.
