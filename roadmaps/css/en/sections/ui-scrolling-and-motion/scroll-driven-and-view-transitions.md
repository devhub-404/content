# Scroll-driven Animations and View Transitions

Scroll-driven animations use scroll or view progress as the animation timeline instead of elapsed time. This is useful for progress indicators and effects that genuinely correspond to scrolling. The same keyframe model is used; only the timeline source changes.

```css
.reading-progress {
  transform-origin: left;
  animation: grow linear both;
  animation-timeline: scroll(root block);
}

@keyframes grow {
  from { scale: 0 1; }
  to   { scale: 1 1; }
}

.product-card {
  view-transition-name: selected-product;
}
```

View transitions animate visual continuity between old and new document states by exposing browser-managed snapshot pseudo-elements. Named elements can be connected across states. Both systems are progressive enhancements: content, navigation, and state changes must remain correct without the animation, and reduced-motion preferences should still be respected.
