# Server Action Security

Hiding a button is not authorization. A Server Action can receive a direct POST from outside the rendered UI, so it must verify identity, object ownership or permissions, and input constraints inside the server boundary every time.

```tsx
"use server";

export async function deleteProject(projectId: string) {
  const session = await verifySession();
  const project = await db.project.findUnique({ where: { id: projectId } });

  if (!project || project.ownerId !== session.userId) {
    throw new Error("Not authorized");
  }

  await db.project.delete({ where: { id: projectId } });
}
```

Use a data-access layer or domain service so authorization rules are difficult to bypass accidentally from another action or Route Handler. Avoid returning database rows with secrets or private fields by default. Audit cache behavior as part of the same authorization model.
