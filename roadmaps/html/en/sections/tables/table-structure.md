# Table Structure and Headers

Use tables for data whose meaning depends on rows and columns. `table` contains rows (`tr`), and rows contain data cells (`td`) or header cells (`th`). `caption` gives the table a name. `thead`, `tbody`, and `tfoot` can group rows into logical regions when that structure is useful.

```html
<table>
  <caption>Orders by month</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Orders</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">January</th>
      <td>120</td>
    </tr>
  </tbody>
</table>
```

Header cells should represent real row or column labels. `scope="col"` and `scope="row"` make simple header relationships explicit and help assistive technology provide context while users navigate cells. Do not create a visual table from generic boxes when the content is tabular, and do not use an HTML table merely to lay out a page.
