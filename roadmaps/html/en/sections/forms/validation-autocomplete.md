# Validation and Autocomplete

HTML can express common validation constraints with attributes such as `required`, `minlength`, `maxlength`, `min`, `max`, `step`, and `pattern`. The browser can prevent a normal submission when a control violates these constraints and expose validity states to CSS and JavaScript.

```html
<input
  name="username"
  required
  minlength="3"
  maxlength="20"
  pattern="[A-Za-z0-9_]+"
  autocomplete="username">
```

`autocomplete` tells the browser what real-world data a field represents, using tokens such as `name`, `email`, `username`, `current-password`, `street-address`, and `postal-code`. Good autocomplete reduces typing and helps password managers. Client-side constraints improve interaction but are not a security boundary; always validate submitted values on the server.
