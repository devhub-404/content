# Combinators

Combinators express relationships. A space means descendant, `>` means direct child, `+` means the immediately following sibling, and `~` means later siblings with the same parent. These relationships are powerful because they let CSS use structure already present in the document.

```css
article p { color: #333; }
article > p { max-inline-size: 68ch; }
h2 + p { margin-block-start: 0; }
h2 ~ p { color: #444; }
```

Use the weakest relationship that expresses the real dependency. `article > p` is appropriate when only direct paragraphs matter, while `article p` also reaches nested paragraphs. Avoid selectors that encode a long accidental DOM path; small markup changes can break them even though the component meaning has not changed.
