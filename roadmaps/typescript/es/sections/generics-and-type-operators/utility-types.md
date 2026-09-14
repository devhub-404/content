# Utility types estándar

TypeScript incluye utilidades como `Partial`, `Required`, `Readonly`, `Pick`, `Omit`, `Record`, `Exclude`, `Extract`, `NonNullable`, `Parameters`, `ReturnType` y `Awaited`. Son combinaciones reutilizables de los mecanismos normales del sistema de tipos.

```ts
type UserPatch = Partial<User>;
type SavedUser = Required<UserDraft>;
type PublicUser = Pick<User, "id" | "name">;
type WithoutSecret = Omit<User, "passwordHash">;
type UserById = Record<string, User>;
```

Úsalas cuando su nombre describa claramente la transformación. No apiles varias solo para evitar un pequeño tipo nombrado. Muchas transformaciones son superficiales: `Readonly<T>` no hace deep freeze ni cambia el comportamiento de runtime.
