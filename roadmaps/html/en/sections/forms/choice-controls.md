# Checkboxes, Radio Buttons, and Select

Checkboxes represent independent on/off choices. Radio buttons represent one choice from a group and belong to the same group when they share a `name`; each radio needs a distinct submitted `value`. `select` presents a controlled list of `option` choices, and `optgroup` can label groups inside longer menus.

```html
<label><input type="checkbox" name="newsletter"> Newsletter</label>

<label><input type="radio" name="plan" value="basic"> Basic</label>
<label><input type="radio" name="plan" value="pro"> Pro</label>

<select name="country">
  <option value="">Choose a country</option>
  <option value="br">Brazil</option>
  <option value="jp">Japan</option>
</select>
```

Use the control whose interaction matches the choice. A short set of mutually exclusive options is often clearer as radios because all choices remain visible. A select is useful when the list is longer or screen space matters. Native choice controls come with keyboard, focus, and accessibility behavior that is expensive to recreate correctly.
