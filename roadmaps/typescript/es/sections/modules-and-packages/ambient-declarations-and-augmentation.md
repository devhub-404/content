# Ambient declarations y module augmentation

Las ambient declarations describen valores o módulos que existen en runtime pero no se definen en el source actual. Global o module augmentation pueden ampliar declarations existentes cuando el runtime también ha sido extendido de verdad.

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

La augmentation solo cambia el checker. Declarar `window.appVersion` no crea esa propiedad. Mantén la declaración cerca del código que hace el patch real y usa este patrón con moderación: las extensiones globales ocultas complican ownership y orden de carga.
