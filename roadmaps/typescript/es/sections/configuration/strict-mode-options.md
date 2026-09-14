# La familia `strict`

`strict` activa un conjunto de checks fuertes, incluidos nullability, implicit any, inicialización y reglas de funciones. Es un buen baseline para proyectos nuevos porque permite al checker hacer afirmaciones más útiles sobre el código común.

```ts
{
  "compilerOptions": {
    "strict": true,
    "noImplicitOverride": true,
    "noUncheckedIndexedAccess": true,
    "exactOptionalPropertyTypes": true
  }
}
```

Opciones como `noUncheckedIndexedAccess`, `exactOptionalPropertyTypes` y `noImplicitOverride` endurecen áreas específicas. Actívalas comprendiendo el modelo que imponen. El trabajo adicional suele reflejar incertidumbre real que ya existía en runtime.
