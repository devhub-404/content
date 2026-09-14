# Forms, Names, and Submission

`form` groups controls that can submit name/value data. `action` identifies the submission destination and `method` chooses the HTTP method used by normal form submission. `get` commonly puts form data in the URL query string; `post` sends it in the request body.

```html
<form action="/search" method="get">
  <label for="q">Search</label>
  <input id="q" name="q" type="search">
  <button type="submit">Search</button>
</form>
```

A successful control needs a `name` to contribute data. The input's `id` connects it to the visible label, while `name="q"` becomes the submitted field name. Forms do not require JavaScript for basic submission. Add scripting to enhance validation, feedback, or application behavior, but keep server-side validation because client markup can be bypassed or modified.
