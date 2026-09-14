# Direction, Focus Hooks, and Editable Content

`dir` expresses base text direction and belongs in HTML when direction is known from the content. `bdi` can isolate a piece of text whose direction is unknown so it does not disturb surrounding bidirectional text. Direction is semantic information; CSS logical properties can then adapt layout to it.

```html
<html lang="ar" dir="rtl">

<p>User <bdi>إياد</bdi> scored 12 points.</p>

<div id="error-summary" tabindex="-1">
  Please correct the highlighted fields.
</div>

<div contenteditable="true">Edit this note.</div>
```

`tabindex="-1"` makes an element programmatically focusable without adding it to normal Tab order; `0` can place an otherwise suitable custom target in sequential focus order. Avoid positive tabindex values because they create a fragile alternate order. `contenteditable` makes content editable, but it does not provide a complete editor: selection, paste, sanitization, undo, storage, and accessibility still require deliberate design.
