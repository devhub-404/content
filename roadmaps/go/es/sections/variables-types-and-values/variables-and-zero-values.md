# Variables y Zero Values

Toda variable Go tiene un zero value definido cuando se declara sin initializer. Los números quedan en cero, bools en false, strings vacías y pointers/interfaces/slices/maps/channels/functions tienen estados nil apropiados.

```go
var count int
var ready bool
var name string

fmt.Println(count, ready, name)
// 0 false ""
```

Diseña tipos para que su zero value sea útil cuando sea posible. Muchos tipos estándar, como `sync.Mutex` y `bytes.Buffer`, pueden usarse inmediatamente. Un zero value útil reduce constructors innecesarios y simplifica inicialización.
