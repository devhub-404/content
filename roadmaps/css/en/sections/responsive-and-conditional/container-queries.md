# Container Queries and Container Units

Container queries let descendants respond to an ancestor container rather than the viewport. `container-type: inline-size` is the common choice for component layout that depends on available inline width; names disambiguate which container a nested component should query.

```css
.card-shell {
  container: card / inline-size;
}

@container card (width >= 32rem) {
  .card {
    display: grid;
    grid-template-columns: 10rem 1fr;
  }
}

.card h2 {
  font-size: clamp(1.2rem, 5cqi, 2rem);
}
```

Container query units such as `cqi` and `cqb` size values relative to an eligible query container. This makes the same component adapt independently in a narrow sidebar and a wide main region. Newer container queries can also test style, scroll state, and anchored-position state; use those progressively and verify support for the exact query type.
