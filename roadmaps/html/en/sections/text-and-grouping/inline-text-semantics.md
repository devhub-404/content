# Useful Inline Text Semantics

HTML includes inline elements for common kinds of text. `abbr` identifies an abbreviation; `code` marks computer code; `kbd` marks user input; `samp` marks sample program output; `sub` and `sup` represent subscript and superscript when that position is part of the meaning; and `time` can pair human-readable text with a machine-readable date or time.

```html
<p><abbr title="HyperText Markup Language">HTML</abbr> structures web content.</p>
<p>Run <code>npm test</code> and press <kbd>Enter</kbd>.</p>
<p>Water is H<sub>2</sub>O and 2<sup>10</sup> is 1024.</p>
<p>Published <time datetime="2026-09-12">September 12, 2026</time>.</p>
```

Other useful elements include `mark` for contextually relevant highlighting, `small` for side comments such as legal text, `cite` for the title of a work, and `q` for a short inline quotation. These elements should be chosen for meaning, not simply because their default styling looks convenient.
