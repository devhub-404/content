# Font Families and Web Fonts

`font-family` is an ordered fallback list. End author stacks with an appropriate generic family such as `sans-serif`, `serif`, or `monospace`; different scripts may fall back to different fonts inside the same line. Font metrics affect line breaks and layout, not just appearance.

```css
body {
  font-family: Inter, system-ui, sans-serif;
}

@font-face {
  font-family: "Brand Sans";
  src: url("/fonts/brand-sans.woff2") format("woff2");
  font-weight: 100 900;
  font-style: normal;
  font-display: swap;
}
```

`@font-face` maps a family/style/weight description to downloadable font data. Declare actual weight and style ranges so the browser can choose the right face instead of synthesizing one. `font-display` controls loading behavior; `swap` favors immediate fallback text followed by the web font. Web fonts are network dependencies, so keep the fallback experience usable.
