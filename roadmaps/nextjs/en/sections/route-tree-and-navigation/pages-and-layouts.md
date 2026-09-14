# Pages and Layouts

A `page` file makes a route segment publicly reachable, while a `layout` wraps pages and nested layouts below its segment. Layouts persist across client navigation, which makes them suitable for shared shells, navigation, providers, and route-level structure.

```tsx
// app/dashboard/layout.tsx
export default function Layout({ children }) {
  return (
    <section>
      <DashboardNav />
      <main>{children}</main>
    </section>
  );
}

// app/dashboard/page.tsx
export default function Page() {
  return <h1>Dashboard</h1>;
}
```

Keep persistent state in a layout only when persistence across its child routes is intentional. Layouts do not receive arbitrary child-page data, so shared data should be fetched where needed or provided through appropriate server/client composition rather than forcing hidden coupling between routes.
