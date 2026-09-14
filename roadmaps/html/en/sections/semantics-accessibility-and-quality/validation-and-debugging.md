# Validation and HTML Debugging

HTML is forgiving enough that invalid markup can still look correct. Validation catches duplicate IDs, invalid nesting, missing required attributes, obsolete constructs, and other conformance problems before they turn into browser-specific surprises. Browser DevTools show the DOM the parser actually created, which can differ from the source after error recovery.

```html
<label for="email">Email</label>
<input id="email" name="email" type="email" required>
```

Validation is necessary but not sufficient. A document can be technically valid while using vague link text, poor heading hierarchy, useless alt text, unlabeled controls, or the wrong semantic element. Review real content with keyboard navigation and accessibility tools, and treat validator errors as structural defects rather than cosmetic lint.
