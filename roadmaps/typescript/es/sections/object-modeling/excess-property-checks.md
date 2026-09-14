# Excess property checks

Los object literals nuevos reciben checks adicionales para propiedades que no existen en el tipo objetivo. Ayudan a detectar typos y campos equivocados en el punto de creación. La regla es más estricta que la asignación estructural general de una variable ya existente.

```ts
interface User {
  name: string;
}

const user: User = {
  name: "Mina",
  // role: "admin", // excess property in this fresh literal
};
```

No resuelvas un error con cast hasta entender si el campo extra es legítimo. Si el objeto acepta realmente claves adicionales, modela esa posibilidad; si es un typo, el checker te está protegiendo. Evita usar assertions para apagar una señal útil.
