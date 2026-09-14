# Form Controls, Focus, and Accent Color

Native form controls have browser and platform styling. Start by inheriting typography and changing spacing, borders, colors, and `accent-color` before removing native appearance. `appearance: none` transfers more responsibility to your CSS and should be used only when the product truly needs custom rendering.

```css
input,
button,
select,
textarea {
  font: inherit;
}

input[type="checkbox"],
input[type="radio"] {
  accent-color: #2457d6;
}

:focus-visible {
  outline: 3px solid Highlight;
  outline-offset: 3px;
}
```

Focus indication is essential for keyboard navigation. `:focus-visible` lets the browser show your focus style when a visible cue is appropriate. Keep touch targets large enough, allow labels and validation text to wrap, and test zoom, forced colors, keyboard, and touch. Styling should enhance native semantics rather than hide the control and rebuild it poorly.
