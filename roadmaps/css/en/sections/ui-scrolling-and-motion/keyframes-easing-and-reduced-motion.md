# Keyframes, Easing, and Reduced Motion

`@keyframes` defines values at points on an animation timeline. The animation properties control name, duration, timing function, delay, iteration count, direction, fill mode, and play state. Easing maps timeline progress to value progress: linear gives constant progress, Bézier curves create acceleration/deceleration, and `steps()` creates discrete changes.

```css
@keyframes pulse {
  0%, 100% { scale: 1; }
  50% { scale: 1.04; }
}

.busy {
  animation: pulse 1.2s ease-in-out infinite;
}

@media (prefers-reduced-motion: reduce) {
  .busy { animation: none; }
}
```

Infinite animation should communicate something useful rather than continuously demand attention. `prefers-reduced-motion` lets users request less non-essential motion. A reduced-motion version can keep color or opacity feedback while removing large movement, zooming, or repeated motion. Treat the preference as a design requirement, not merely a performance switch.
