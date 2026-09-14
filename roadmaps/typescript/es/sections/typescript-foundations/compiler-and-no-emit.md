# Type checking, emisión y `noEmit`

El compilador TypeScript puede comprobar tipos y emitir JavaScript, pero ambas tareas pueden separarse. Muchos proyectos modernos usan otra herramienta para transpilar o bundle y ejecutan `tsc --noEmit` solo como typechecker. Otros dejan que `tsc` genere JavaScript y declarations.

```ts
{
  "compilerOptions": {
    "strict": true,
    "noEmit": true
  }
}
```

Define claramente qué herramienta se encarga de type checking, transformación de sintaxis, bundling, minificación y emisión de `.d.ts`. Un transpile exitoso no implica type check exitoso. Ejecuta el checker de forma deliberada en CI en lugar de asumir que el build ya lo hizo.
