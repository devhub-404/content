# Null, Undefined, and Strict Null Checking

With `strictNullChecks`, `null` and `undefined` are distinct types and must be handled before a value is used as a non-null type. This matches real JavaScript behavior more closely and prevents a large class of property-access and call errors.

```ts
function findUser(id: string): User | undefined {
  return users.find(user => user.id === id);
}

const user = findUser("u1");
if (user) {
  console.log(user.name);
}
```

Model absence honestly: a search might return `T | undefined`, a field might be optional, and an API might deliberately use null. Do not scatter non-null assertions merely to silence the checker; `value!` is a promise from you to TypeScript and adds no runtime check. Prefer control flow or better initialization when possible.
