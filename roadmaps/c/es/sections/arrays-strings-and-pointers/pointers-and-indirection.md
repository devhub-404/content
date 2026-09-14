# Punteros e Indirección

Un puntero almacena una dirección o valor de puntero referido a un objeto, función o posición one-past según las reglas de C. `&` obtiene la dirección y `*` hace dereference para acceder al objeto.

```c
int value = 42;
int *ptr = &value;

*ptr = 50;
printf("%d
", value);
```

El puntero debe ser válido para la operación y estar relacionado con un objeto cuyo lifetime siga activo. Dereference de un puntero null, dangling, no inicializado o inválido es undefined behavior. Trata validez y ownership como invariantes explícitas.
