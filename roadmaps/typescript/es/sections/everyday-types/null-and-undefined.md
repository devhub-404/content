# Null, undefined y strict null checking

Con `strictNullChecks`, `null` y `undefined` son tipos distintos y deben tratarse antes de usar un valor como no-null. Esto se parece mucho más al comportamiento real de JavaScript y evita una gran clase de errores de acceso a propiedades.

```ts
function findUser(id: string): User | undefined {
  return users.find(user => user.id === id);
}

const user = findUser("u1");
if (user) {
  console.log(user.name);
}
```

Modela la ausencia honestamente: una búsqueda puede devolver `T | undefined`, un campo puede ser opcional y una API puede usar null. No abuses de `!` para silenciar el checker; la non-null assertion no añade ningún check de runtime.
