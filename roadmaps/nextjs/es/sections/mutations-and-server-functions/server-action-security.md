# Seguridad de Server Actions

Ocultar un button no es authorization. Una Server Action puede recibir un POST directo fuera de la UI, por lo que debe verificar identity, ownership/permissions e input constraints dentro de la server boundary siempre.

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

Usa data-access layer/domain service para que authorization sea difícil de saltar desde otra action/Route Handler. No retornes rows con secrets/private fields por defecto. Audita cache como parte del mismo authorization model.
