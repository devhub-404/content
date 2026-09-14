# Data Validation and Safe Serialization

Values from forms, route params, JSON, cookies, headers, and external services are untrusted until validated at the boundary that consumes them. TypeScript types disappear at runtime and do not validate a request. Use schemas or explicit checks for runtime data.

```tsx
const input = CreateUserSchema.parse({
  email: formData.get("email"),
  name: formData.get("name")
});

const userView = {
  id: user.id,
  name: user.name
};
```

Return only fields the caller needs. Passing an ORM entity into a Client Component can serialize private columns or create future leaks when the model grows. Narrow view models make security review, cache safety, and compatibility easier than passing “everything” and filtering later.
