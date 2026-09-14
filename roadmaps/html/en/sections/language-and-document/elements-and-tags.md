# Elements, Tags, and Void Elements

Most HTML elements have a start tag, content, and an end tag. In `<p>This is a paragraph.</p>`, the complete construct is the `p` element, while `<p>` and `</p>` are its tags. Elements can contain text and other elements when their content model allows it.

```html
<p>This is a paragraph.</p>
<img src="photo.jpg" alt="A mountain at sunrise">
<br>
```

Some elements are void elements and cannot contain content or have an end tag. Common examples include `img`, `input`, `meta`, `link`, `br`, `hr`, `source`, and `track`. Writing `<img></img>` does not turn an image into a container. Learn the content rules of each element instead of assuming every tag comes in a pair.
