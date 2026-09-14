# Strings, Bytes e Runes

String em Go é sequência imutável de bytes e convencionalmente contém UTF-8, mas nem toda string precisa ser UTF-8 válido. `len` conta bytes, indexação retorna byte e `range` decodifica runes UTF-8 informando posições em bytes.

```go
text := "Olá, 世界"

fmt.Println(len(text)) // bytes

for i, r := range text {
    fmt.Println(i, r)
}
```

`byte` é alias de `uint8` e `rune` de `int32` para code points Unicode. Um caractere percebido pode ter várias runes. Converta entre `string`, `[]byte` e `[]rune` conscientemente porque muitas conversões alocam.
