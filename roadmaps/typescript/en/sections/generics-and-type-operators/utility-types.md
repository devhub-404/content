# Standard Utility Types

TypeScript ships utility types for common transformations: `Partial`, `Required`, `Readonly`, `Pick`, `Omit`, `Record`, `Exclude`, `Extract`, `NonNullable`, `Parameters`, `ReturnType`, `Awaited`, and others. They compose ordinary type-system features into reusable vocabulary.

```ts
type UserPatch = Partial<User>;
type SavedUser = Required<UserDraft>;
type PublicUser = Pick<User, "id" | "name">;
type WithoutSecret = Omit<User, "passwordHash">;
type UserById = Record<string, User>;
```

Use a utility when its name clearly matches the domain transformation. Do not stack several utilities merely to avoid defining a small readable named type. Some utilities are shallow because TypeScript's property modifiers are shallow; `Readonly<T>` does not recursively freeze nested values or change runtime mutability.
