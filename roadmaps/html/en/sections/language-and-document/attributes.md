# Attributes and Boolean Attributes

Attributes add information or configuration to an element and are written in its start tag. `href` gives a link its destination; `class` assigns reusable class names; `id` identifies an element; form attributes such as `required` affect control behavior. Attribute names and allowed values depend on the element and the attribute definition.

```html
<a href="/about" class="nav-link">About</a>
<button disabled>Save</button>
<input required>
```

Boolean attributes work by presence: if `disabled` is present, the button is disabled; if `required` is present, the control is required. Writing `disabled="false"` still means disabled because the attribute is present. Quote ordinary attribute values consistently, especially when they can contain spaces or punctuation.
