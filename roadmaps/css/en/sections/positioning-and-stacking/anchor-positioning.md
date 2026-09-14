# Anchor Positioning

Anchor positioning lets a positioned element use another element as a geometric anchor. It is designed for UI such as menus, tooltips, callouts, and popovers that should stay attached to a trigger without manual JavaScript geometry. Anchor functions can also reference anchor position or size.

```css
.trigger {
  anchor-name: --menu-trigger;
}

.menu {
  position: absolute;
  position-anchor: --menu-trigger;
  position-area: block-end span-inline-end;
}
```

The model includes fallback placements so the browser can try another position when the preferred one would overflow. Anchor positioning is a modern feature, so verify the exact subset supported by your browser baseline and preserve a usable fallback. It handles geometry; it does not replace the semantic or interaction behavior of a popover, dialog, menu, or tooltip.
