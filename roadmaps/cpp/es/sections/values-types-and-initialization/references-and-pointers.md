# Referencias y Punteros

Una referencia es un alias ligado a un objeto o función y no se reseata como un puntero después de inicializarse. Un puntero es un objeto que guarda un valor de puntero, puede ser null, reasignarse y soporta operaciones según las reglas del lenguaje.

```cpp
int value = 42;

int &ref = value;
int *ptr = &value;

ref = 50;
*ptr = 60;
```

Usa referencias para aliases obligatorios y punteros cuando optionality, reseating o semántica de pointer formen parte de la interfaz. Ni raw pointer ni reference expresan ownership por sí solos; las APIs modernas deben hacer visible el ownership mediante valores o smart pointers.
