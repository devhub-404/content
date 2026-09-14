# Margin Collapsing and Block Formatting Contexts

Adjacent block-axis margins in normal block flow can collapse instead of adding together. Parent and first/last-child margins can also collapse in specific conditions. Flex and grid item margins do not collapse. This behavior is why two paragraphs with `margin-block: 1rem` do not necessarily have a 2rem gap.

```css
.stack > * + * {
  margin-block-start: 1rem;
}

.isolated {
  display: flow-root;
}
```

A block formatting context isolates several block-flow interactions, including float containment and some margin relationships. `display: flow-root` is the direct way to create one without switching to flex or grid. For predictable vertical rhythm, one-direction spacing patterns such as adding margin only between adjacent children are easier to reason about than symmetric margins everywhere.
