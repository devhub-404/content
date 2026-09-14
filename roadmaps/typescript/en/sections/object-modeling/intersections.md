# Intersection Types

An intersection `A & B` describes a value that satisfies both types at once. For object types this often combines sets of required properties. Intersections are useful for composition, mixin-like helpers, and APIs that add capabilities to an existing shape.

```ts
type Timestamped = {
  createdAt: Date;
};

type Entity = {
  id: string;
};

type StoredEntity = Entity & Timestamped;
```

Intersections are not object-spread operations and can become impossible when the same property is required with incompatible types. Prefer defining a clear named object contract when repeated intersections become difficult to read. Unions model alternatives; intersections model simultaneous requirements.
