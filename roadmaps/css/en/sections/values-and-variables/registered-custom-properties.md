# Registered Custom Properties with `@property`

`@property` registers a custom property with a syntax, inheritance behavior, and initial value. Registration gives the browser type information that ordinary `--*` variables do not have. That can make values validate earlier, receive a controlled initial value, and interpolate in animations when the declared type is animatable.

```css
@property --progress {
  syntax: "<number>";
  inherits: false;
  initial-value: 0;
}

.bar {
  --progress: .65;
  scale: var(--progress) 1;
}
```

Use registration when the variable behaves like part of a component API and type information provides real value. Ordinary custom properties remain simpler for most tokens. The Properties and Values API also has a JavaScript registration form; both mechanisms describe the same kind of typed custom property.
