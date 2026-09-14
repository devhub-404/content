# Typed Arrays e Dados Binários

`ArrayBuffer` representa memória binária bruta. Views typed array como `Uint8Array`, `Int16Array` e `Float32Array` interpretam essa memória como elementos numéricos de largura fixa. `DataView` fornece reads e writes de nível menor com offsets de byte e endianness explícitos.

```js
const buffer = new ArrayBuffer(8);
const bytes = new Uint8Array(buffer);
const numbers = new Uint32Array(buffer);

bytes[0] = 255;
console.log(numbers[0]);
```

Typed arrays possuem muitos métodos semelhantes aos de arrays, mas são views de tamanho fixo com regras de conversão numérica. São importantes para arquivos, protocolos, gráficos, áudio, compressão, interfaces criptográficas e WebAssembly. Conheça layout e byte order do formato externo; bytes corretos interpretados com tipo errado continuam sendo dados errados.
