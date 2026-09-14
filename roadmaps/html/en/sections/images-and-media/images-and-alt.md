# Images and Alternative Text

`img` embeds an image that is part of the document content. `src` identifies the resource and `alt` provides a text alternative. The right alt text depends on the image's purpose in context: describe the information the reader needs, not simply that “an image” exists.

```html
<img
  src="mountain.jpg"
  alt="Snow-covered mountain above a pine forest"
  width="1200"
  height="800">
```

Decorative images that add no information should normally use `alt=""` so assistive technology can ignore them. Do not omit `alt` from ordinary content images. Supplying intrinsic `width` and `height` lets the browser calculate the aspect ratio before the image loads, which helps reserve space and reduce layout shift. CSS can still render the image responsively at another size.
