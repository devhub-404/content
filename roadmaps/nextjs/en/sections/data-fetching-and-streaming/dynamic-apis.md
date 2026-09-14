# Dynamic APIs and Request-time Data

APIs such as `cookies`, `headers`, and request-specific search parameters read values that are not known at build time. Their use therefore participates in dynamic rendering decisions, especially under Cache Components where uncached request-time work must be isolated from prerendered or cached content.

```tsx
import { cookies } from "next/headers";

export default async function Page() {
  const cookieStore = await cookies();
  const theme = cookieStore.get("theme")?.value ?? "light";
  return <main data-theme={theme}>...</main>;
}
```

Read request data only where it is actually needed. Putting dynamic access in the root layout can make a large part of the application request-dependent. Keep personalized regions narrow and use Suspense or cache boundaries according to the framework's current rendering model.
