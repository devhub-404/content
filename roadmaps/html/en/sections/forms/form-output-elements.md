# `datalist`, `output`, `meter`, and `progress`

`datalist` supplies suggestions to a compatible input without restricting the user to those suggestions. It is different from `select`, where the choices are controlled. Native datalist interfaces vary between browsers, so use it for lightweight suggestions rather than critical selection workflows.

```html
<input name="city" list="cities">
<datalist id="cities">
  <option value="Lisbon">
  <option value="Tokyo">
</datalist>

<output>$48</output>
<meter min="0" max="100" value="72">72%</meter>
<progress max="100" value="40">40%</progress>
```

`output` represents a calculation or action result. `meter` represents a scalar measurement within a known range, such as a score or storage usage. `progress` represents completion progress for a task. Although meter and progress can look similar, they describe different concepts and should not be substituted for each other solely for appearance.
