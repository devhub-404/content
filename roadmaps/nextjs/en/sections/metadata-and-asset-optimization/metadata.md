# Metadata API

Server route files can export static `metadata` or an async `generateMetadata` function, and special files can define favicons, manifests, robots, sitemaps, and Open Graph images. Next.js turns this structured metadata into the corresponding document head elements.

```tsx
export const metadata = {
  title: "Store",
  description: "Products and offers"
};

export default function Page() {
  return <h1>Store</h1>;
}
```

Generate dynamic metadata from the same canonical data source as the page to avoid title, URL, or availability mismatches. Metadata is not only SEO: correct titles, descriptions, social cards, canonical URLs, and robots behavior affect users, crawlers, and link previews.
