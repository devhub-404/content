# Utility Types Padrão

TypeScript fornece utility types para transformações comuns: `Partial`, `Required`, `Readonly`, `Pick`, `Omit`, `Record`, `Exclude`, `Extract`, `NonNullable`, `Parameters`, `ReturnType`, `Awaited` e outros. Eles compõem recursos normais do sistema de tipos em vocabulário reutilizável.

```ts
type UserPatch = Partial<User>;
type SavedUser = Required<UserDraft>;
type PublicUser = Pick<User, "id" | "name">;
type WithoutSecret = Omit<User, "passwordHash">;
type UserById = Record<string, User>;
```

Use utility quando seu nome corresponde claramente à transformação de domínio. Não empilhe várias apenas para evitar definir pequeno tipo nomeado e legível. Algumas são rasas porque modifiers do TypeScript são rasos; `Readonly<T>` não congela recursivamente valores aninhados nem muda mutabilidade em runtime.
