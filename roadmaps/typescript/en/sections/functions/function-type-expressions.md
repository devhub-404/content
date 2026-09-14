# Function Type Expressions and Call Signatures

Function type expressions describe callable values concisely. Object type call signatures are useful when a callable value also has properties. TypeScript checks parameter and return compatibility when functions are assigned or passed as callbacks.

```ts
type Formatter = (value: number) => string;

type Describable = {
  description: string;
  (value: number): string;
};
```

Distinguish a function's runtime declaration syntax from the type that describes callable behavior. Type aliases for important callbacks can make event, pipeline, and dependency APIs easier to read. Avoid annotating every local arrow function when contextual typing already supplies the correct parameter and return expectations.
