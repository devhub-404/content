# User Preference and Input Capability Queries

Media features can describe user preferences such as reduced motion, color scheme, contrast, and forced colors, as well as input capabilities such as hover and pointer accuracy. These features are more reliable than inferring interaction style from viewport size.

```css
@media (prefers-reduced-motion: reduce) {
  .panel { transition: none; }
}

@media (prefers-color-scheme: dark) {
  :root { --surface: #161616; --text: #f5f5f5; }
}

@media (hover: hover) and (pointer: fine) {
  .menu-item:hover { text-decoration: underline; }
}
```

Treat preference queries as part of normal product behavior, not after-the-fact polish. A large touchscreen may have a coarse pointer, and a small device may have a precise pointer, so query the capability you actually need. The default experience must remain usable when no enhancement query matches; hover should never be the only route to essential information.
