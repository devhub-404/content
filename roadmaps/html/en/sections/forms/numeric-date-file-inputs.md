# Numeric, Date, Range, Color, and File Inputs

HTML includes specialized input types for common value domains. `number` can express `min`, `max`, and `step`; `range` provides a slider-like control for an approximate value; date and time types can provide platform pickers; `color` can provide a color picker; and `file` lets the user choose local files.

```html
<input type="number" name="qty" min="1" max="10" step="1">
<input type="range" name="volume" min="0" max="100">
<input type="date" name="start">
<input type="color" name="accent">
<input type="file" name="receipt" accept="image/*,.pdf">
```

Native interfaces vary by browser and operating system, so choose a type for its data semantics rather than expecting identical visuals everywhere. `accept` on file inputs is only a selection hint, not security validation. File type, size, and contents must still be checked on the server, and file-upload forms normally use `multipart/form-data`.
