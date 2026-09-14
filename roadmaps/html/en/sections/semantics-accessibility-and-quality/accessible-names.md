# Accessible Names

Interactive controls and embedded content need names that tell users what they are. Different elements obtain names in different native ways: form controls from labels, images from `alt`, buttons from their text content, and iframes from `title`. Visible text is usually the strongest starting point because it helps everyone.

```html
<label for="search">Search products</label>
<input id="search" name="q" type="search">

<img src="warning.svg" alt="Warning: high voltage">

<iframe src="/chart" title="Quarterly revenue chart"></iframe>
```

Do not add `aria-label` reflexively when native visible content already provides the correct name. Accessible-name computation has specific precedence rules, and an ARIA label can replace visible text in the accessibility tree. Use ARIA naming when native mechanisms are unavailable or insufficient, and test the resulting name with accessibility tooling.
