# Text Alignment and Decoration

`text-align` controls inline alignment; logical `start` and `end` follow writing direction and are usually more portable than left/right. Justification changes spacing to align both edges and should be tested with the actual language and column width. Letter and word spacing can also affect readability and should not be used to force arbitrary visual fit.

```css
.article {
  text-align: start;
}

.article a {
  text-decoration-thickness: .08em;
  text-underline-offset: .18em;
}
```

Text decoration properties control underline line, style, thickness, offset, and skipping behavior; text emphasis marks serve writing systems where emphasis is conventionally shown beside glyphs. When customizing links, preserve a recognizable affordance. Text shadows and decoration affect painting but do not change the underlying line-box geometry.
