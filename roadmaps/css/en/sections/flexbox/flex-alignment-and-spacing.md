# Flex Alignment, Gaps, and Auto Margins

`justify-content` distributes items or free space on the main axis. `align-items` aligns items on the cross axis, and `align-self` overrides one item. `gap` creates consistent spacing between items without adding unwanted outer margins. `align-content` applies to multiple flex lines, not ordinary alignment inside one line.

```css
.nav {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.nav__account {
  margin-inline-start: auto;
}
```

Auto margins absorb available free space and are useful for pushing a single item or group away from siblings. In the example, the account item moves to the inline end without relying on `space-between`. Because axes follow `flex-direction`, check the direction before deciding that an alignment property is acting “backwards.”
