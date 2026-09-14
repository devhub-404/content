# Iframes and Embedded Documents

`iframe` embeds another browsing context inside the current page. Give it a useful `title` so users can identify the frame before entering it. Width and height provide an initial geometry, and off-screen frames can be candidates for lazy loading.

```html
<iframe
  src="/embedded/map"
  title="Store location map"
  width="640"
  height="400"
  loading="lazy"
  sandbox>
</iframe>
```

The `sandbox` attribute applies a set of restrictions to embedded content; tokens can selectively restore capabilities when required. Sandboxing is a security feature with subtle rules, so grant only the permissions the embedded document needs. Iframes are heavier and more isolated than normal elements: use them when content truly belongs in another document context, not as a generic component mechanism.
