# Cell Spans and Complex Tables

`rowspan` and `colspan` let a cell cover several row or column positions. They are useful for hierarchical headers, totals, and grouped data, but they also make the relationship graph more complex. Prefer the simplest table structure that accurately represents the data.

```html
<table>
  <tr>
    <th rowspan="2">Region</th>
    <th colspan="2">Revenue</th>
  </tr>
  <tr>
    <th>Q1</th>
    <th>Q2</th>
  </tr>
  <tr>
    <th>North</th>
    <td>$42k</td>
    <td>$48k</td>
  </tr>
</table>
```

For complex tables, test how header context is announced by assistive technology. Explicit `id` and `headers` associations exist for cases where simple row and column scopes are not enough. Responsive design should preserve the data relationships: horizontal scrolling is often safer than turning each row into unrelated blocks that lose their column context.
