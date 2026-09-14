# Declaration Merging and Namespaces

Some declarations with the same name merge, notably interfaces and certain namespace combinations. This supports extensible library contracts and patterns used by existing JavaScript ecosystems. It also means an interface can be intentionally open rather than a closed one-time declaration.

```ts
interface Box {
  width: number;
}

interface Box {
  height: number;
}

const box: Box = {
  width: 10,
  height: 20,
};
```

Namespaces are a legacy TypeScript organization mechanism that predates widespread ECMAScript modules. They remain relevant in declaration files and existing code, but TypeScript 6.0 deprecates legacy module-oriented patterns around namespaces for new project configuration. Prefer standard ES modules for ordinary application and library source.
