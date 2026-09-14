# App Router and the Legacy Pages Router

Next.js still documents the older Pages Router for existing applications, but new framework capabilities are centered on the App Router. App Router uses nested layouts, Server Components by default, streaming boundaries, Route Handlers, and Server Functions rather than `getServerSideProps` or `getStaticProps`.

```tsx
// Modern route
// app/dashboard/page.tsx
export default function DashboardPage() {
  return <Dashboard />;
}
```

Do not mix mental models casually. A migration can run both routers in one project, but each route belongs to one system and has different data/rendering conventions. For new learning and new routes, start from App Router unless a project's existing architecture requires Pages Router compatibility.
