# Numbers, Dimensions, and Percentages

CSS values are typed by context. Unitless numbers, lengths, angles, times, resolutions, percentages, colors, images, identifiers, and other types appear in different property grammars. A length such as `16px` is not interchangeable with an angle or time, and a unitless number can have a completely different meaning from the same digits with a unit.

```css
.box {
  inline-size: 20rem;
  rotate: 5deg;
  transition-duration: 200ms;
  opacity: .8;
  max-inline-size: 80%;
}
```

Percentages are relative values, but their reference depends on the property. `width: 50%` is normally resolved against a containing block's inline size, while other percentage properties can use different references. Do not learn `%` as simply “relative to the parent”; check what the property defines. Zero often needs no length unit, but typed contexts can still require an angle, time, or other dimension.
