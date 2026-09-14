# Responsive Layout Before Breakpoints

Responsive CSS begins with flexible flow and constraints, not a list of device widths. Let blocks use available space, images stay inside containers, text wrap, Flexbox wrap when appropriate, Grid create intrinsic tracks, and min/max constraints keep content within useful bounds.

```css
.page {
  inline-size: min(72rem, calc(100% - 2rem));
  margin-inline: auto;
}

img {
  max-inline-size: 100%;
  block-size: auto;
}
```

Add a conditional rule when the design needs a discrete change, such as moving from one column to two. Choose that threshold from the content: resize until the current arrangement becomes cramped or until extra space creates a useful new option. Responsive design also includes zoom, user fonts, orientation, input method, and long localized content—not only viewport width.
