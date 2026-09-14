# How the Cascade Chooses a Value

When several declarations can set the same property on the same element, CSS uses the cascade. First, a declaration must be relevant: the selector must match and enclosing conditions must be true. Then CSS compares cascade origin and importance, layer order, specificity, scoping proximity, and finally source order.

```css
.message { color: navy; }
.message { color: rebeccapurple; }
```

These two declarations tie until source order, so the second wins. “Last rule wins” is therefore only a final tie-breaker, not the whole cascade. When debugging, first ask whether the rule matched, then which origin/layer it belongs to, then specificity and scope, and only then whether later source order decides the result.
