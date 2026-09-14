# Pages y Layouts

Un file `page` hace accesible un route segment y un `layout` envuelve pages/layouts inferiores. Los layouts persisten durante client navigation, sirviendo para shells, navigation, providers y estructura compartida.

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

Mantén state persistente en layout solo cuando la persistencia entre child routes sea intencional. Los layouts no reciben data arbitraria de pages; shared data debe fetched donde corresponda o componerse mediante boundaries adecuadas.
