# Links, URLs, and Link Text

An `a` element with `href` is a hyperlink. The URL can be absolute, root-relative, document-relative, a fragment, or another supported scheme. Use links when the user is navigating to another resource or location; use buttons for actions that change application state without navigation.

```html
<a href="/pricing">View pricing</a>
<a href="guide.html">Read the guide</a>
```

Link text should make sense in context and, when possible, out of context. “View pricing” is more useful than repeated “click here.” Relative URLs are resolved from the current document or configured base URL, while an absolute URL includes its scheme and host. Choose the simplest URL form that correctly identifies the destination.
