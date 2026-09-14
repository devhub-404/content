# Comparators y Projections

Muchos ranges algorithms aceptan comparators y projections. Una projection transforma cada elemento para comparar sin crear un range temporal, útil para sort/search por un member.

```cpp
std::ranges::sort(users, {}, &user::name);

auto found = std::ranges::find(
    users,
    "Mina",
    &user::name
);
```

Los comparators deben satisfacer el contrato de ordering del algoritmo; romper strict weak ordering puede producir resultados incorrectos o UB. Prefiere utilities estándar y projections simples frente a comparators manuales que duplican acceso a campos.
