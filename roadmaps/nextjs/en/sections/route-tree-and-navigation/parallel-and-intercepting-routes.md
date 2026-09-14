# Parallel and Intercepting Routes

Parallel routes render named slots in one layout, while intercepting routes let one navigation render another route inside the current layout context. Together they support patterns such as a photo modal on client navigation while the same photo has a standalone URL on direct load.

```tsx
app/
  @modal/
    (.)photo/[id]/page.tsx
  photo/[id]/page.tsx
  layout.tsx
```

These conventions are powerful but increase route-tree complexity. Use them for genuine multi-pane or modal routing behavior where URL/history semantics matter. If a simple component state toggle is enough, it is easier to understand and test than advanced filesystem routing syntax.
