# Replaced Elements and Object Fitting

Images, video, and some controls are replaced elements: their external content has intrinsic dimensions that participate in sizing. `aspect-ratio` supplies a preferred ratio when one dimension is automatic, helping responsive media reserve predictable geometry.

```css
.thumbnail {
  inline-size: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
  object-position: 50% 35%;
}
```

`object-fit` controls how replaced content fits its content box. `cover` fills the box and crops excess; `contain` preserves the entire object with possible letterboxing; `fill` can distort. `object-position` chooses the focal alignment. Do not force unrelated width and height values that stretch content; choose a fitting strategy that preserves the intended image geometry.
