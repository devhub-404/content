# Language, Charset, and Viewport

Three declarations belong near the beginning of most documents. `lang` identifies the document's primary language, which helps pronunciation, translation, spellchecking, and language-sensitive processing. `meta charset="utf-8"` tells the browser how bytes map to Unicode characters.

```html
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
  </head>
</html>
```

The viewport declaration makes the CSS layout viewport follow the device width on mobile browsers and establishes a normal initial scale. Avoid viewport settings that prevent zoom, because users may depend on zoom for readability. If a subsection switches language, add a more specific `lang` attribute to that element rather than changing the whole document.
