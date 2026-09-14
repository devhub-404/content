# Typed arrays y datos binarios

`ArrayBuffer` representa memoria binaria bruta. Views como `Uint8Array`, `Int16Array` y `Float32Array` interpretan esos bytes como elementos numéricos de tamaño fijo. `DataView` permite lecturas y escrituras de bajo nivel con offsets y endianness explícitos.

```js
const buffer = new ArrayBuffer(8);
const bytes = new Uint8Array(buffer);
const numbers = new Uint32Array(buffer);

bytes[0] = 255;
console.log(numbers[0]);
```

Son importantes para archivos, protocolos, gráficos, audio, compresión, criptografía y WebAssembly. Tienen métodos parecidos a arrays pero reglas de conversión y tamaño distintas. Conoce el layout de bytes y el byte order del formato externo; interpretar correctamente los bytes es parte del contrato de datos.
