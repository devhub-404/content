# `hidden` and `inert`

`hidden` says that an element is not currently relevant for presentation. A hidden element is not rendered in the normal way. `inert` is different: it makes a subtree non-interactive and removes ordinary focus and accessibility interaction while the subtree can remain visible.

```html
<section hidden>
  <h2>Draft report</h2>
</section>

<main inert>
  ...
</main>
```

Use them for the state they actually represent. Content that is not currently part of the presented UI can be hidden; content temporarily unavailable because another interaction owns attention may be inert. Native modal dialogs already manage background inertness, so do not add overlapping mechanisms unless the product has a separate reason.
