# Metadata API

Los server route files pueden exportar `metadata` estático o `generateMetadata` async, y special files definen favicon, manifest, robots, sitemap y OG images. Next transforma la estructura en head elements.

```tsx
export const metadata = {
  title: "Store",
  description: "Products and offers"
};

export default function Page() {
  return <h1>Store</h1>;
}
```

Genera dynamic metadata desde la misma canonical data source de la page para evitar mismatch de title/URL. Metadata no es solo SEO: titles, social cards, canonical URLs y robots afectan users, crawlers y previews.
