# Symbols y hooks de protocolo

Un Symbol es un primitivo único muy útil como property key sin colisionar con strings normales. `Symbol()` crea uno nuevo y `Symbol.for()` usa un registry global. Muchas operaciones de enumeración de strings omiten propiedades con clave Symbol.

```js
const internalId = Symbol("internalId");

const record = {
  [internalId]: 42,
  [Symbol.toStringTag]: "Record",
};
```

Los well-known symbols definen protocolos y hooks del lenguaje para iteración, conversión primitiva, matching, disposal, tags y otros comportamientos. Implementa estos hooks solo cuando tu tipo realmente participa en el protocolo. Symbol ofrece identidad, no privacidad ni seguridad.
