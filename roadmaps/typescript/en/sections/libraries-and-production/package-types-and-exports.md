# Package Types and Export Maps

A published package must align its JavaScript entry points and type entry points. Modern package export maps can expose different subpaths and conditions, and TypeScript's module resolver uses that metadata according to the configured environment.

```ts
{
  "name": "example-lib",
  "type": "module",
  "exports": {
    ".": {
      "types": "./dist/index.d.ts",
      "import": "./dist/index.js"
    }
  }
}
```

Do not publish declarations for paths that consumers cannot import at runtime, or runtime paths with no corresponding types when the library promises typed support. Test a packed or published artifact from a small consumer project. Local source aliases can hide packaging mistakes that appear only after installation.
