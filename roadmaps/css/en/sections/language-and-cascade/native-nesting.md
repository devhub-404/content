# Native CSS Nesting

Native nesting lets related selectors and conditional rules live inside a parent style rule. A nested selector can begin with a combinator, and `&` explicitly represents the parent selector when needed for states or more complex combinations.

```css
.card {
  padding: 1rem;

  > h2 {
    margin-block-start: 0;
  }

  &:hover {
    border-color: #888;
  }

  @media (width >= 40rem) {
    padding: 1.5rem;
  }
}
```

Nesting changes organization, not the underlying cascade. The effective selector still has specificity and can become brittle if you create deep chains. Keep nesting shallow enough that the resulting relationship is obvious. Nested `@media` or `@container` rules can be useful because a component's responsive changes stay close to its base styles.
