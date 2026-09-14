# Transforms

Transforms move, rotate, scale, skew, or otherwise change an element's rendered coordinate system after layout. They do not make neighboring normal-flow boxes reserve new space. Individual `translate`, `rotate`, and `scale` properties are convenient when effects should be controlled independently.

```css
.badge {
  translate: 0 -.15em;
  rotate: -2deg;
}

.button:active {
  scale: .98;
}
```

The order of functions in a traditional `transform` list matters because each operation changes the coordinate system for the next. `transform-origin` changes the pivot for rotation and scaling. Three-dimensional transforms add a z axis and perspective; use them deliberately because large spatial movement can affect readability and motion comfort. Transforms often create stacking contexts.
