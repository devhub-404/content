# Validação de Dados e Serialization Segura

Values de forms, params, JSON, cookies, headers e external services são não confiáveis até runtime validation. TypeScript types somem em runtime e não validam request. Use schemas/checks explícitos.

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

Retorne apenas fields necessários. Passar ORM entity para Client Component pode serializar private columns ou vazar no futuro. View models estreitos facilitam security review, cache safety e compatibility.
