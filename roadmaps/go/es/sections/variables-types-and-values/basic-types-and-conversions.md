# Tipos Básicos y Conversiones

Go tiene tipos enteros, floating-point, complex, boolean, string y tipos relacionados con byte/rune. Existen `int`/`uint` dependientes de la máquina y nombres fixed-width como `int32` y `uint64`. Los tipos nombrados son distintos aunque compartan representación subyacente.

```go
var age int = 42
var ratio float64 = 0.75
var enabled bool = true
var text string = "Go"

converted := float64(age)
```

Go no realiza conversiones numéricas implícitas amplias como lenguajes C-like. Las conversiones son explícitas, haciendo visibles cambios de signo o precisión. Usa `int` para counts/indexes normales salvo cuando un protocolo o rango exija anchura específica.
