# Excess Property Checks

Fresh object literals receive extra checks for properties that are not known on the target type. This catches likely typos or mistaken fields at creation sites. The rule is intentionally stricter than general structural assignment, where a variable may contain additional properties and still be compatible.

```ts
interface User {
  name: string;
}

const user: User = {
  name: "Mina",
  // role: "admin", // excess property in this fresh literal
};
```

Do not work around an excess-property error with a cast until you understand whether the extra field is actually intended. If the object legitimately supports more keys, model them with an explicit index signature or a broader domain type. If it is a typo, the extra check is doing useful work.
