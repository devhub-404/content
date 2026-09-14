# The HTML Document Skeleton

A normal HTML document starts with the HTML doctype, has one root `html` element, a `head` for document metadata, and a `body` for the content presented to the user. The doctype keeps the browser in standards mode; it is not an HTML element.

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>My page</title>
  </head>
  <body>
    <h1>Hello</h1>
  </body>
</html>
```

`lang` declares the main document language. Inside `head`, UTF-8 is the standard character encoding, the viewport declaration enables expected responsive behavior on mobile browsers, and `title` names the document in browser UI such as tabs and bookmarks. Visible page content belongs in `body`. This skeleton is a reliable starting point for ordinary pages.
