# Bit-fields, Alignment y Layout

Los bit-fields permiten que miembros de una struct ocupen un número especificado de bits, pero el orden, packing y varios detalles son implementation-defined. Pueden servir para hardware específico, pero no son una buena opción para formatos portables de red o archivo.

```c
struct flags {
    unsigned ready : 1;
    unsigned error : 1;
    unsigned mode  : 2;
};
```

Para formatos binarios externos, codifica y decodifica explícitamente con máscaras y shifts y define el byte order. Usa `alignof`, `alignas`, `sizeof` y static assertions cuando el layout importe y verifica las suposiciones en cada ABI.
