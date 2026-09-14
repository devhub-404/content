# Typed Arrays and Binary Data

`ArrayBuffer` represents raw binary memory. Typed-array views such as `Uint8Array`, `Int16Array`, and `Float32Array` interpret that memory as fixed-width numeric elements. `DataView` gives lower-level reads and writes with explicit byte offsets and endianness.

```js
const buffer = new ArrayBuffer(8);
const bytes = new Uint8Array(buffer);
const numbers = new Uint32Array(buffer);

bytes[0] = 255;
console.log(numbers[0]);
```

Typed arrays have many array-like methods but are fixed-length views with numeric conversion rules. They are important for files, network protocols, graphics, audio, compression, cryptography interfaces, and WebAssembly boundaries. Know the external format's byte layout and byte order; the right bytes interpreted with the wrong type are still wrong data.
