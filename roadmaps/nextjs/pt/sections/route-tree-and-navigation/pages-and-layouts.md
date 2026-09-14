# Pages e Layouts

File `page` torna route segment acessível e `layout` envolve pages/layouts abaixo. Layouts persistem durante client navigation, servindo a shells, navigation, providers e estrutura compartilhada.

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

Mantenha state persistente no layout somente quando persistência entre child routes é intencional. Layouts não recebem data arbitrária das pages; shared data deve ser fetched onde necessário ou composto por boundaries adequadas.
