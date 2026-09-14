# Route Groups and Private Folders

Parentheses create route groups that organize files or select different layouts without adding a URL segment. Underscore-prefixed private folders opt a subtree out of routing and are useful for colocated components, tests, or implementation modules inside the `app` tree.

```tsx
app/
  (marketing)/
    about/page.tsx
    pricing/page.tsx
  (app)/
    dashboard/page.tsx
  _components/
    Logo.tsx
```

Use groups to express layout or organizational boundaries, not to create a second invisible routing system. Two groups cannot resolve to the same URL. Private folders are optional because files are not routable until a `page` or `route` convention exposes them, but they make intent explicit.
