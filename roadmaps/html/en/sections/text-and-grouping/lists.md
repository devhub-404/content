# Lists

HTML has three main list structures. `ul` is an unordered list when sequence is not important. `ol` is an ordered list when order or numbering matters. Both contain `li` list items. Lists can be nested when the content is genuinely hierarchical.

```html
<ul>
  <li>Tea</li>
  <li>Coffee</li>
</ul>

<ol>
  <li>Open the package.</li>
  <li>Add water.</li>
</ol>

<dl>
  <dt>HTML</dt>
  <dd>Structures web content.</dd>
</dl>
```

A description list uses `dl`, `dt`, and `dd` for name-description groups. It works for glossaries, metadata, terms with definitions, and similar relationships. Do not choose a list only to get bullets or numbers from the browser. Use list markup when the content is actually a list, then let CSS control markers and layout.
