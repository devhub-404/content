# Comparators e Projections

Muitos ranges algorithms aceitam comparators e projections. Projection transforma cada elemento para comparação sem criar range temporário, útil para sort/search por um member.

```cpp
std::ranges::sort(users, {}, &user::name);

auto found = std::ranges::find(
    users,
    "Mina",
    &user::name
);
```

Comparators precisam satisfazer o contrato de ordering do algoritmo; strict weak ordering quebrada pode tornar resultados incorretos ou UB. Prefira comparison utilities e projections simples a comparators manuais duplicando acesso a campos.
