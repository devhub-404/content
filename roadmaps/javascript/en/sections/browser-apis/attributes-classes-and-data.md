# Attributes, Classes, and Data Attributes

DOM elements expose JavaScript properties and HTML attributes. Many properties reflect attributes, but the exact reflection rules differ. Use the property intended for live state when one exists, such as `input.value` or `button.disabled`, and attribute methods when you need the literal serialized attribute.

```js
button.disabled = true;
button.classList.toggle("is-active", active);
button.dataset.userId = String(user.id);

const label = button.getAttribute("aria-label");
```

`classList` adds, removes, toggles, and tests classes without parsing a class string. `dataset` maps `data-*` attributes to strings. Boolean HTML attributes are represented by presence; setting an attribute to the text `"false"` still leaves it present. Understand the HTML feature's semantics before choosing a DOM manipulation method.
