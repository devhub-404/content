# Function type expressions y call signatures

Una function type expression describe un valor invocable, por ejemplo `(value: number) => string`. Un object type también puede incluir una call signature cuando el mismo valor es callable y tiene propiedades.

```ts
type Formatter = (value: number) => string;

type Describable = {
  description: string;
  (value: number): string;
};
```

El tipo de una función es distinto de la sintaxis que la implementa. Aliases para callbacks importantes pueden mejorar APIs de eventos, pipelines o dependencias. No anotes arrows locales innecesariamente si contextual typing ya proporciona los parámetros correctos.
