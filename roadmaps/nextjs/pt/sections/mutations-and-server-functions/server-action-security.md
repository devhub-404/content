# Segurança de Server Actions

Esconder button não é authorization. Server Action pode receber POST direto fora da UI, então precisa verificar identity, ownership/permissions e input constraints dentro da server boundary sempre.

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

Use data-access layer/domain service para authorization ser difícil de bypass em outra action/Route Handler. Não retorne rows com secrets/private fields por default. Audite cache como parte do mesmo authorization model.
