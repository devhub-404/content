# Enumeraciones

Un enum introduce constantes enteras con nombre y un tipo de enumeración. Sirve para estados discretos, flags con una representación diseñada por separado y APIs donde los nombres simbólicos comunican mucho más que enteros crudos.

```c
enum status {
    STATUS_PENDING,
    STATUS_READY,
    STATUS_FAILED
};

enum status state = STATUS_READY;
```

No supongas que un enum impide automáticamente valores enteros arbitrarios provenientes de casts, I/O o datos corruptos. Valida enteros externos antes de interpretarlos como estados. C23 mejora los enums, pero una API portable debe documentar el conjunto válido.
