# Validación de Datos y Serialization Segura

Values de forms, params, JSON, cookies, headers y external services no son confiables hasta runtime validation. Los TypeScript types desaparecen en runtime y no validan una request. Usa schemas/checks explícitos.

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

Retorna solo fields necesarios. Pasar una ORM entity a un Client Component puede serializar private columns o filtrar datos en el futuro. View models estrechos facilitan security review, cache safety y compatibility.
