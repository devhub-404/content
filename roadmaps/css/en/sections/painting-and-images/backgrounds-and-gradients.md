# Background Layers and Gradients

A background can contain a color and multiple image layers. Each layer can have independent position, size, repeat, origin, and clipping behavior. The first listed image is painted closest to the viewer; the background color sits behind all image layers.

```css
.hero {
  background:
    linear-gradient(rgb(0 0 0 / .55), rgb(0 0 0 / .15)),
    url("/images/hero.jpg") center / cover no-repeat;
  color: white;
}
```

Linear, radial, and conic gradients are generated images, so they can be used anywhere an image value is accepted and layered with ordinary images. `cover` fills the background area and may crop the source; `contain` keeps the whole image visible and may leave unused space. Background images are decorative: content images that need alternative text belong in HTML.
