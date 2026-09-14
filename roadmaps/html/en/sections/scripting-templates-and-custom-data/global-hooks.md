# `id`, `class`, and `data-*`

`id` identifies an element within the document and must be unique when used as an identifier. It supports fragment navigation, label/control relationships, ARIA relationships, scripting, and styling. `class` provides one or more reusable class names and is the common hook for CSS component and utility styles.

```html
<section id="pricing" class="panel featured">
  <button data-product-id="sku-4182">Add to cart</button>
</section>
```

Custom attributes beginning with `data-` store application-specific data on an element and are available to JavaScript through `dataset`. Use them for data that genuinely belongs to your application, not to reinvent standard attributes. IDs, classes, and data attributes are hooks; they do not give the content semantic meaning by themselves.
