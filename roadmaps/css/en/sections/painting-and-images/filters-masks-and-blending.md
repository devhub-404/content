# Filters, Clipping, Masking, and Blending

`filter` processes an element's rendered output; `backdrop-filter` processes pixels behind a translucent element. Blend modes change how overlapping layers combine. `clip-path` creates a hard visible region, while masks can create partial transparency and soft edges using alpha or luminance.

```css
.photo { filter: saturate(.9) contrast(1.05); }
.avatar { clip-path: circle(45%); }

.fade-edge {
  mask-image:
    linear-gradient(to right, transparent, black 15%, black 85%, transparent);
}
```

These effects change painting and compositing rather than normal-flow geometry. A circular clip does not make surrounding content lay out around a circle. Complex blurs, filters, and animated masks can be expensive, especially across large surfaces. Do not rely on blending or translucency for essential text contrast because the background can change the result.
