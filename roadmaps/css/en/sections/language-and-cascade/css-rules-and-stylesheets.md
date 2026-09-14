# CSS Rules and Stylesheets

CSS is a stylesheet language: selectors choose elements and declarations assign values to properties. A declaration block can contain many property/value pairs, and a stylesheet can contain style rules, comments, and at-rules such as `@media`, `@supports`, and `@layer`.

```css
p {
  color: navy;
  font-size: 1.1rem;
}
```

External stylesheets are the normal choice for reusable site styles. A `<style>` block is useful for document-specific rules, while inline `style` attributes are best reserved for narrow dynamic cases because they participate in the cascade with unusually strong author precedence. Keep CSS responsible for presentation; keep document meaning in HTML.
