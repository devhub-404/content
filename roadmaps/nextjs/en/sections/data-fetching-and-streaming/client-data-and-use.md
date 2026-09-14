# Client Data and React `use`

A Server Component can start a promise and pass the promise to a Client Component, where React's `use` API reads it under Suspense. This lets server work begin early while a client boundary controls how and when the result appears.

```tsx
// Server Component
const commentsPromise = getComments(postId);
return <Comments commentsPromise={commentsPromise} />;

// Client Component
"use client";
function Comments({ commentsPromise }) {
  const comments = use(commentsPromise);
  return comments.map(c => <p key={c.id}>{c.body}</p>);
}
```

Use the pattern when the client boundary genuinely needs the result or interactive presentation. Otherwise, await and render data on the server. Promises passed across the boundary must be supported by the React/Next serialization model, and errors should have an appropriate boundary.
