# `main`, `header`, and `footer`

`main` identifies the dominant content of the document body. A page normally has one active main region; repeated site navigation, branding, and footer content do not belong inside it unless they are actually the page's primary purpose. This creates a useful landmark for navigation.

```html
<body>
  <header>Site header...</header>
  <main>
    <h1>Account settings</h1>
    ...
  </main>
  <footer>Site footer...</footer>
</body>
```

`header` and `footer` are relative to the section they belong to. A page can have a site header and footer, while an `article` can also have its own header and footer for title/byline and author/update information. Their meaning is contextual, not simply “the box at the top” and “the box at the bottom.”
