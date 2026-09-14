# Specificity and Inheritance

Specificity compares selectors after stronger cascade criteria are tied. IDs contribute more specificity than classes, attributes, and pseudo-classes; those contribute more than type selectors and pseudo-elements. Combinators add no specificity. `:where()` is special because it always contributes zero.

```css
p { color: black; }
.note { color: navy; }
#warning { color: crimson; }

article {
  color: #333;
  font-family: system-ui;
}
```

Inheritance is a separate mechanism. Some properties, especially text-related ones such as `color` and many font properties, normally inherit from the parent; box and layout properties generally do not. `inherit` explicitly takes the parent's computed value, while `initial`, `unset`, `revert`, and `revert-layer` choose other fallback points. Keep selectors low enough that ordinary overrides do not require specificity escalation.
