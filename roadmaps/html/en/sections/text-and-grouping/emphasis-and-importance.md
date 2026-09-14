# Emphasis and Importance

`em` marks stress emphasis: changing the emphasized word can change the nuance of the sentence. `strong` marks strong importance, seriousness, or urgency. Browsers often render `em` in italics and `strong` in bold, but those visual defaults are not the meaning of the elements.

```html
<p>You <em>must</em> stir continuously.</p>
<p><strong>Warning:</strong> the surface is hot.</p>
```

If text is only visually different, do not invent emphasis semantics just to obtain italics or bold. Use the element that matches the content meaning, then style it with CSS. This distinction matters because assistive technologies and other software can use semantics even when the visual presentation is completely changed.
