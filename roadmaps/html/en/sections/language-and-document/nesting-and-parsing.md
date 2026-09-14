# Nesting and Browser Parsing

HTML elements can be nested, but not every element is allowed inside every other element. Close nested elements in the reverse order they were opened, and respect each element's content model. Correct nesting makes the intended tree clear to both people and tools.

```html
<p>
  Read the <strong>important note</strong> first.
</p>
```

HTML parsing is deliberately error-tolerant. When markup is invalid, the browser often repairs it and builds a DOM anyway. That means the DOM can differ from the source you thought you wrote, especially around paragraphs, tables, forms, and interactive content. Do not rely on error recovery as a coding style. When structure behaves unexpectedly, inspect the DOM in DevTools and validate the markup.
