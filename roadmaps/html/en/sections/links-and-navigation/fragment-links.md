# Fragment Links and IDs

A URL fragment beginning with `#` points to an element whose `id` matches the fragment. This enables tables of contents, skip links, deep links, and navigation to specific regions of a document. IDs used as targets must be unique within the document.

```html
<a href="#shipping">Jump to shipping</a>

<section id="shipping">
  <h2>Shipping</h2>
  <p>Orders leave within two business days.</p>
</section>
```

Fragments are part of the URL, so a user can bookmark or share the specific location. Keep IDs stable when links may exist outside the page. CSS can use `scroll-margin` to keep a fragment target from being covered by sticky UI, but the target relationship itself belongs in HTML.
