# Forms and `FormData`

HTML forms already provide submission, labels, controls, and constraint validation. JavaScript can listen for `submit`, inspect form controls, call `checkValidity()` or `reportValidity()`, and create `FormData` from successful named controls. Listening to the form preserves keyboard and other native submission paths.

```js
form.addEventListener("submit", event => {
  if (!form.checkValidity()) {
    event.preventDefault();
    form.reportValidity();
    return;
  }

  const data = new FormData(form);
  console.log(data.get("email"));
});
```

Client validation is user feedback, not a security boundary; the server must validate submitted data again. `FormData` can also be sent directly through Fetch for multipart-style data. Preserve native form semantics and progressively enhance them instead of replacing working controls with custom div-based widgets.
