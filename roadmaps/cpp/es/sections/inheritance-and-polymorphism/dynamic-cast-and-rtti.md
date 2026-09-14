# RTTI y `dynamic_cast`

RTTI soporta operaciones como `dynamic_cast` y `typeid` en tipos polimórficos. `dynamic_cast` puede comprobar y convertir de forma segura a lo largo de una jerarquía cuando el diseño realmente necesita conocer el tipo dinámico.

```cpp
shape &s = get_shape();

if (auto *c = dynamic_cast<circle *>(&s)) {
    std::cout << c->area() << '
';
}
```

Downcasts frecuentes suelen indicar una interfaz base incompleta o que un modelo variant/value sería más claro. Usa RTTI en fronteras que realmente requieran type discovery, no como mecanismo principal de dispatch ordinario.
