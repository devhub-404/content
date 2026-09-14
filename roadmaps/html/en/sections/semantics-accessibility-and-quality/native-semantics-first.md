# Native HTML First

Native elements already provide semantics and often behavior. A button is focusable, keyboard-activatable, disableable, and exposed as a button to assistive technology. A link with `href` participates in navigation and browser link behavior. Starting from generic `div` elements means rebuilding contracts the platform already provides.

```html
<button type="button">Save changes</button>

<a href="/account">Open account</a>
```

ARIA can supplement HTML when native semantics do not express a required state or relationship, but it does not automatically add keyboard behavior. Prefer the native element whose built-in contract matches the task. Use a button for an action, a link for navigation, a heading for a heading, and a real form control for user input.
