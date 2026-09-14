# Qué añade TypeScript a JavaScript

TypeScript es JavaScript con un sistema de tipos estático y una capa de tooling. Comprueba programas antes de ejecutarlos, puede inferir muchos tipos a partir de JavaScript normal y elimina la sintaxis puramente tipada al emitir JavaScript. El runtime sigue ejecutando JavaScript.

```ts
function greet(name: string): string {
  return `Hello, ${name}`;
}

greet("Mina");
// greet(42); // type error
```

El typechecker detecta errores como llamadas inválidas, propiedades inexistentes o datos incompatibles, pero no prueba todos los hechos de runtime. Los datos externos siguen necesitando validación. Aprende primero la semántica de JavaScript: TypeScript la describe y la verifica, no la sustituye.
