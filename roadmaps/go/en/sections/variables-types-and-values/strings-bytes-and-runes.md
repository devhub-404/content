# Strings, Bytes, and Runes

A Go string is an immutable sequence of bytes and conventionally holds UTF-8 text, but the language does not require every string to contain valid UTF-8. `len(s)` counts bytes, indexing returns a byte, and `range` over a string decodes UTF-8 runes and reports byte positions.

```go
text := "Olá, 世界"

fmt.Println(len(text)) // bytes

for i, r := range text {
    fmt.Println(i, r)
}
```

`byte` is an alias for `uint8` and `rune` an alias for `int32` used for Unicode code points. User-perceived characters can contain multiple runes, so UI-level grapheme handling may need a higher-level Unicode library. Convert between `string`, `[]byte`, and `[]rune` deliberately because conversions allocate in many cases.
