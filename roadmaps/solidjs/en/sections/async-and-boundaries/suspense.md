# Suspense

`Suspense` coordinates UI that depends on async resources. While data inside the boundary is pending, Solid can show a fallback and later reveal the resolved content. Boundaries can be nested so unrelated parts of a page do not wait for one slow resource.

```tsx
<Suspense fallback={<p>Loading user…</p>}>
  <UserProfile user={user} />
</Suspense>
```

Place boundaries around meaningful loading regions, not every individual text node. Suspense coordinates rendering; it does not decide caching or request policy by itself. Keep useful existing content visible when that produces a better experience than replacing an entire area with a spinner.
