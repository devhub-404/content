# App Router y Pages Router Legado

Next.js aún documenta el Pages Router antiguo, pero las capabilities modernas se centran en App Router. Usa nested layouts, Server Components por defecto, streaming, Route Handlers y Server Functions en vez de `getServerSideProps`/`getStaticProps`.

```tsx
// Modern route
// app/dashboard/page.tsx
export default function DashboardPage() {
  return <Dashboard />;
}
```

No mezcles modelos casualmente. Una migration puede mantener ambos, pero cada route pertenece a un sistema con conventions distintas. Para aprendizaje y routes nuevas, empieza con App Router salvo que una arquitectura existente exija Pages Router.
