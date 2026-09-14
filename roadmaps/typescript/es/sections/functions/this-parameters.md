# Tipar parámetros `this`

TypeScript permite declarar un primer parámetro ficticio llamado `this` para describir el receiver esperado por una función ordinaria. Se elimina al emitir JavaScript y no cambia la convención de llamada; solo comprueba que el receiver sea compatible.

```ts
interface User {
  name: string;
}

function greet(this: User, message: string) {
  return `${message}, ${this.name}`;
}

const user = { name: "Mina", greet };
user.greet("Hello");
```

Es útil en callbacks y APIs que dependen de `this` dinámico. Las arrows no usan este patrón porque su `this` es léxico. Si una API no necesita realmente semántica de receiver, parámetros explícitos suelen ser más fáciles de probar y componer.
