# React Server Components

A Server Component renders in a server or build environment before its result is sent to the client. It can access server-side data and dependencies directly and does not add its own component code to the client bundle. Server Components may be async.

```jsx
async function Note({ id }) {
  const note = await db.notes.get(id);
  return <article>{note.body}</article>;
}
```

Server Components cannot use client interaction Hooks such as `useState`. They compose with Client Components when part of the UI needs browser APIs or events. React defines the model, but an application normally uses Server Components through a framework that implements the bundling and transport protocol.
