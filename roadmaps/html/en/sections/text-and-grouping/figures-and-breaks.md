# Figures, Captions, and Thematic Breaks

`figure` groups self-contained content such as an image, chart, code sample, quotation, or table when that item can be treated as a unit. `figcaption` provides its caption and can appear first or last inside the figure. Not every image needs a figure; use it when the image and caption form a meaningful unit.

```html
<figure>
  <img src="sales-chart.png" alt="Sales rise from January through June.">
  <figcaption>Monthly sales, January–June.</figcaption>
</figure>

<hr>
```

`hr` represents a thematic break in the content, such as a scene change or topic transition. Its common horizontal-line appearance is only the default styling. If you only need a decorative border between boxes, CSS is a better tool than adding an `hr` with no thematic meaning.
