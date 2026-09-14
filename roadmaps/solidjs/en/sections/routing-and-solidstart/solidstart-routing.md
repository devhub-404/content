# SolidStart File-based Routing

SolidStart builds a full-stack framework around Solid and Solid Router. In v2, files under `src/routes` define UI and API routes, with filename conventions for static, dynamic, optional, and catch-all segments. Route nesting creates reusable layouts and boundaries.

```tsx
// src/routes/users/[id].tsx
export default function UserPage() {
  const params = useParams();
  return <h1>User {params.id}</h1>;
}
```

Use file routing to express the URL tree, not the internal component folder structure. Keep route-level data and server concerns near the route when that improves ownership, while moving reusable domain logic into ordinary modules. SolidStart v2 itself is still tied to the broader Solid 2 migration timeline.
