# `textarea` and Buttons

`textarea` collects multi-line text. Its initial value goes between the start and end tags, not in a `value` attribute. `rows` and `cols` provide an initial size hint, while CSS normally controls the final layout. Be aware that literal whitespace between the tags can become part of the initial value.

```html
<label for="message">Message</label>
<textarea id="message" name="message" rows="6"></textarea>

<button type="submit">Send</button>
<button type="button">Preview</button>
```

A `button` inside a form defaults to submit behavior, so specify `type` when intent could be ambiguous. Use `submit` to submit, `button` for script-driven actions, and `reset` only when restoring all initial values genuinely helps the user. Outside forms, a button remains the correct native element for actions such as opening a menu or dialog.
