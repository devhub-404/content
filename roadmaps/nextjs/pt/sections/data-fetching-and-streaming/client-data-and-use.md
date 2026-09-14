# Client Data e React `use`

Server Component pode iniciar promise e passá-la a Client Component, onde React `use` lê sob Suspense. Isso começa trabalho server cedo enquanto client boundary controla apresentação.

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

Use quando client boundary realmente precisa do resultado/interação. Caso contrário, await/render no server. Promises cruzando boundary precisam ser suportadas pelo modelo React/Next e errors devem ter boundary adequada.
