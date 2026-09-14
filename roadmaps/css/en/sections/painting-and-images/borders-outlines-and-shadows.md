# Borders, Radius, Outlines, and Shadows

Borders occupy box space; border radius rounds border and background corners. Rounded corners do not automatically clip overflowing descendants unless overflow behavior also clips them. Box shadows are painted effects outside or inside the box and do not change layout size.

```css
.card {
  border: 1px solid rgb(0 0 0 / .15);
  border-radius: 1rem;
  box-shadow: 0 .75rem 2rem rgb(0 0 0 / .18);
}

.card :focus-visible {
  outline: 3px solid Highlight;
  outline-offset: 3px;
}
```

Outlines are drawn without taking layout space and are especially useful for focus indicators. Do not remove focus outlines globally. Shadows and subtle borders can support visual hierarchy, but important boundaries and state should remain understandable in high-contrast or forced-color environments where author paint may be changed.
