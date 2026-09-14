# Labels, Fieldsets, and Legends

Every form control needs an accessible name. A `label` connected with matching `for` and `id` is the standard pattern, and wrapping a control inside a label is also valid. Visible labels remain available while the user types; placeholder text does not replace them.

```html
<label for="email">Email address</label>
<input id="email" name="email" type="email">

<fieldset>
  <legend>Delivery speed</legend>
  <label><input type="radio" name="speed" value="standard"> Standard</label>
  <label><input type="radio" name="speed" value="express"> Express</label>
</fieldset>
```

`fieldset` groups related controls and `legend` names the group. This is especially valuable for radio buttons and related checkboxes because each option needs the group question as context. Use native form relationships before reaching for ARIA; browsers already expose these relationships consistently.
