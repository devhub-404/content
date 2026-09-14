# Error and Not-found Boundaries

Route conventions such as `error`, `not-found`, and `global-error` let the App Router render safe fallback UI for different failure scopes. `notFound()` expresses an expected missing resource, while Error Boundaries catch unexpected rendering failures in their subtree.

```tsx
// app/dashboard/error.tsx
"use client";

export default function Error({ error, reset }) {
  return (
    <div>
      <p>Could not load the dashboard.</p>
      <button onClick={reset}>Try again</button>
    </div>
  );
}
```

Do not turn ordinary validation or permissions into generic 500 errors. Model expected domain outcomes deliberately, log unexpected failures with enough server context, and avoid exposing stack traces or secret details to users. A reset button should only be offered when retrying can plausibly succeed.
