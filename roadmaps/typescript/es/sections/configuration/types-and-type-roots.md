# Paquetes de tipos ambient y `types`

Los paquetes de tipos ambient pueden añadir globals y declarations, por ejemplo mediante `@types`. La opción `types` permite escoger explícitamente qué paquetes contribuyen al scope global del proyecto.

```ts
{
  "compilerOptions": {
    "types": ["node", "vitest/globals"]
  }
}
```

En TypeScript 6.0 el default pasa a ser una lista vacía, haciendo estas dependencias globales más explícitas. Los tipos de módulos importados siguen resolviéndose normalmente; la opción afecta principalmente a declarations globales que aparecerían sin import.
