# Client Data y React `use`

Un Server Component puede iniciar una promise y pasarla a un Client Component, donde React `use` la lee bajo Suspense. Esto inicia trabajo server temprano mientras la client boundary controla la presentación.

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

Usa el patrón cuando la client boundary realmente necesite el resultado/interacción. En otro caso, await/render en server. Las promises que cruzan la boundary deben ser compatibles con el modelo React/Next y los errors deben tener una boundary adecuada.
