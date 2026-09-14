# `details` and `summary`

`details` creates a disclosure widget and `summary` provides the visible control that toggles it. The browser supplies pointer and keyboard behavior without custom JavaScript. The `open` attribute represents the expanded state and can also be present initially.

```html
<details>
  <summary>Shipping details</summary>
  <p>Orders leave within two business days.</p>
</details>
```

Use disclosure for optional content that can be shown or hidden in place. It is not a replacement for every expandable interface: menus, modal dialogs, tabs, and application-specific controls have different interaction models. Starting from the native element is valuable because the semantics and basic behavior already exist.
