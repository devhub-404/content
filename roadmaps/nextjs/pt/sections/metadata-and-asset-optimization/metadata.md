# Metadata API

Server route files podem exportar `metadata` estático ou `generateMetadata` async, e special files definem favicon, manifest, robots, sitemap e OG images. Next transforma estrutura em head elements.

```tsx
export const metadata = {
  title: "Store",
  description: "Products and offers"
};

export default function Page() {
  return <h1>Store</h1>;
}
```

Gere dynamic metadata da mesma canonical data source da page para evitar mismatch de title/URL. Metadata não é só SEO: titles, social cards, canonical URLs e robots afetam users, crawlers e previews.
