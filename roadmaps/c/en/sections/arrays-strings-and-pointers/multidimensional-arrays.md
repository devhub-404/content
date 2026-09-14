# Multidimensional Arrays

A multidimensional C array is an array whose elements are themselves arrays. Its storage is contiguous in row-major order for ordinary nested arrays. The inner dimensions are part of the type and are needed when pointer arithmetic steps between rows.

```c
int matrix[2][3] = {
    {1, 2, 3},
    {4, 5, 6},
};

printf("%d
", matrix[1][2]);
```

Function parameters for multidimensional arrays must describe enough dimensions for the compiler to compute addressing, or use a flat buffer plus explicit dimensions/strides. Choose one representation and document the layout; silently assuming a shape is a common interoperability bug.
