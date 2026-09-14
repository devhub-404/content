# App Router e Pages Router Legado

Next.js ainda documenta Pages Router antigo, mas capabilities modernas se concentram no App Router. Ele usa nested layouts, Server Components default, streaming, Route Handlers e Server Functions em vez de `getServerSideProps`/`getStaticProps`.

```tsx
// Modern route
// app/dashboard/page.tsx
export default function DashboardPage() {
  return <Dashboard />;
}
```

Não misture modelos casualmente. Uma migration pode manter ambos, mas cada route pertence a um sistema com conventions diferentes. Para aprendizado e routes novas, comece no App Router salvo arquitetura existente exigir Pages Router.
