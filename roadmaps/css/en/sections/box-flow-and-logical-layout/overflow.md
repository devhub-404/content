# Overflow and Scroll Containers

Overflow occurs when content does not fit its box. `overflow: auto` can create a scroll container when needed; `scroll` always requests scrolling behavior; `hidden` clips overflow while retaining some programmatic scrolling behavior; `clip` is stricter clipping. The inline and block axes can be controlled separately.

```css
.code-frame {
  max-inline-size: 100%;
  overflow: auto;
}

.long-token {
  overflow-wrap: anywhere;
}
```

Do not hide overflow before finding its cause. A flex/grid child may need permission to shrink, text may need wrapping, or a media element may need a max size. Wide code and data tables often deserve local scrolling, while prose should usually wrap. Global `overflow-x: hidden` is a common way to conceal a layout bug rather than solve it.
