# Whitespace, Wrapping, and Hyphenation

`white-space` controls how spaces and line breaks are collapsed and whether lines wrap. `overflow-wrap` lets otherwise unbreakable content wrap when necessary; `word-break` changes word-breaking behavior more aggressively; `hyphens` can enable language-aware hyphenation when language metadata and dictionaries are available.

```css
.prose {
  max-inline-size: 68ch;
  hyphens: auto;
}

.long-token {
  overflow-wrap: anywhere;
}

pre {
  white-space: pre-wrap;
}
```

Use the least disruptive tool that keeps content inside its available inline size. Long URLs may need `overflow-wrap: anywhere`; ordinary prose should not be broken at arbitrary letters. `pre-wrap` is useful when source whitespace matters but lines still need to wrap. Correct HTML language metadata is important for language-sensitive breaking and hyphenation.
