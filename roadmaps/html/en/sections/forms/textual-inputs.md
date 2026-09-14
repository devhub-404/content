# Textual Input Types

The `input` element changes behavior according to its `type`. Common textual types include `text`, `email`, `password`, `search`, `url`, and `tel`. Specialized types can provide useful browser validation and device-appropriate input interfaces, such as an email-focused keyboard on mobile.

```html
<input type="text" name="name">
<input type="email" name="email">
<input type="password" name="password">
<input type="search" name="q">
<input type="url" name="website">
<input type="tel" name="phone">
```

Choose the type that matches the data, but do not confuse browser validation with full business validation. `email` can check basic email syntax; it cannot tell whether the account exists. `tel` intentionally does not enforce one universal phone format because phone numbering varies around the world. Server-side validation remains authoritative.
