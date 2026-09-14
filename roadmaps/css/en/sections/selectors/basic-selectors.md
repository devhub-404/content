# Type, Class, ID, and Universal Selectors

Type selectors match element names, class selectors match tokens in `class`, ID selectors match an `id`, and the universal selector `*` matches elements without adding specificity. Classes are usually the best reusable styling hook because they can be shared without the high specificity of IDs.

```css
p { color: #333; }
.note { background: #fff8c5; }
#main-title { letter-spacing: -.02em; }
* { box-sizing: border-box; }
```

Selector lists separated by commas let several selectors share a declaration block. Keep selectors tied to stable meaning or component structure instead of long DOM paths. An ID is valid CSS, but using IDs as routine styling hooks often makes later overrides unnecessarily difficult.
