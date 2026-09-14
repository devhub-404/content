# `div`, `span`, and Generic Grouping

`div` and `span` are generic containers with no special content meaning. `div` is used for grouping flow content; `span` is used within phrasing content. They are useful when you need a CSS or JavaScript hook and no more specific semantic element describes the relationship.

```html
<div class="price">
  <span class="amount">$29</span>
  <span class="currency">USD</span>
</div>
```

Generic containers are not bad HTML; unnecessary generic containers are. Before adding a `div`, ask whether the content is actually a section, article, navigation region, list, figure, form, or another native structure. Use the semantic element when one fits, and use `div` or `span` honestly when the grouping is purely technical or presentational.
