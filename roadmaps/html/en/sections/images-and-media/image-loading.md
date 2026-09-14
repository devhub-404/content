# Image Loading and Fetch Priority

`loading="lazy"` lets the browser postpone fetching an off-screen image until it is closer to being needed. It is useful for long pages and galleries, but it is usually a poor choice for the main image visible immediately because delaying that resource can hurt perceived and measured loading performance.

```html
<img
  src="gallery-12.jpg"
  alt="Ceramic bowl with blue glaze"
  width="800"
  height="600"
  loading="lazy">

<img
  src="hero.jpg"
  alt="Team working in the studio"
  fetchpriority="high">
```

`fetchpriority` is a hint about relative request priority. Use it sparingly for resources you have identified as unusually important or unimportant; browser scheduling already accounts for many factors. Loading attributes are performance hints, not semantics. They do not replace correct alt text, dimensions, responsive sources, or image optimization.
