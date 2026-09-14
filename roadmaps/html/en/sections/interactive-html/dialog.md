# Dialogs

`dialog` represents a dialog box. JavaScript can show it non-modally with `show()` or modally with `showModal()`, and modern declarative commands can control dialogs without a custom click handler. A modal dialog participates in the top layer and the browser handles important focus and background-inert behavior.

```html
<dialog id="confirm-delete">
  <p>Delete this file?</p>
  <form method="dialog">
    <button value="cancel">Cancel</button>
    <button value="delete">Delete</button>
  </form>
</dialog>
```

A form inside a dialog can use `method="dialog"` so submission closes the dialog instead of sending a network request; the activated submit button can provide a return value. Use the native element instead of a generic `div` when the UI is truly a dialog, because reproducing focus, escape dismissal, modality, and accessibility correctly is subtle.
