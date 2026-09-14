# Popovers

The `popover` global attribute creates content that is hidden until shown in the top layer. `popovertarget` on a button can control it declaratively. The default `auto` mode supports light dismiss and coordinates with other automatic popovers; `manual` leaves opening and closing under explicit control, while newer hint behavior targets transient hint-like UI.

```html
<button popovertarget="help">Help</button>

<div id="help" popover>
  <p>Your order number appears on the receipt.</p>
</div>
```

Popover is display behavior, not a semantic role. A popover can contain help text, navigation, controls, or another meaningful structure, so choose the element and content semantics separately. Because parts of the popover feature set are newer than core HTML, check the browser baseline for the exact behavior you rely on.
