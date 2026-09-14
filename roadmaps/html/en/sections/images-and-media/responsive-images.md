# Responsive Images with `srcset`, `sizes`, and `picture`

Responsive images solve two different problems. `srcset` with width descriptors plus `sizes` lets the browser choose an efficient resolution for the same visual content. The browser combines the candidate widths, the expected rendered slot size, device pixel density, and other factors to choose a resource.

```html
<img
  src="photo-800.jpg"
  srcset="photo-480.jpg 480w,
          photo-800.jpg 800w,
          photo-1200.jpg 1200w"
  sizes="(width <= 600px) 100vw, 800px"
  alt="A cyclist crossing a stone bridge">

<picture>
  <source media="(width < 600px)" srcset="portrait-crop.jpg">
  <img src="wide-photo.jpg" alt="Chef preparing bread at a work table">
</picture>
```

`picture` is useful for art direction or format switching. Art direction means a different crop or composition is more useful in another layout. Format switching offers alternatives such as AVIF or WebP with an `img` fallback. In both cases, the `img` remains the actual image element and owns the alternative text.
