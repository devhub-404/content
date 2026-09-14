# Strings, Bytes y Runes

Una string Go es una secuencia inmutable de bytes y convencionalmente contiene UTF-8, pero no toda string debe ser UTF-8 válido. `len` cuenta bytes, la indexación devuelve un byte y `range` decodifica runes UTF-8 indicando posiciones en bytes.

```go
text := "Olá, 世界"

fmt.Println(len(text)) // bytes

for i, r := range text {
    fmt.Println(i, r)
}
```

`byte` es alias de `uint8` y `rune` de `int32` para code points Unicode. Un carácter percibido puede contener varias runes. Convierte entre `string`, `[]byte` y `[]rune` deliberadamente porque muchas conversiones asignan memoria.
