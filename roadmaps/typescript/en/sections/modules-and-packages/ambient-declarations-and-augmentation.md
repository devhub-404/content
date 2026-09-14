# Ambient Declarations and Module Augmentation

Ambient declarations describe values or modules that exist at runtime but are not defined in the current TypeScript source. Module and global augmentation can add declarations to existing types when a real runtime extension also exists.

```ts
declare global {
  interface Window {
    appVersion: string;
  }
}

declare module "some-library" {
  interface Options {
    traceId?: string;
  }
}

export {};
```

Augmentation changes only the type system. If you declare that `window.appVersion` exists but no script creates it, runtime code still fails. Keep augmentations close to the code that performs the runtime patch and use them sparingly; hidden global extensions make ownership and dependency order difficult to understand.
