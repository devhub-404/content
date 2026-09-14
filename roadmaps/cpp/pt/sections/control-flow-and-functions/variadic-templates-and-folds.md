# Variadic Templates e Fold Expressions

Parameter pack representa zero ou mais argumentos de template ou função. Pack expansion aplica sintaxe aos elementos e fold expressions reduzem o pack com operador binário em uma ordem definida.

```cpp
template <typename... Ts>
auto sum(Ts... values) {
    return (values + ...);
}

auto total = sum(1, 2, 3, 4);
```

Variadic templates sustentam tuples, formatting, factories e forwarding, mas mensagens de erro podem ficar difíceis quando o pack atravessa muitas camadas. Mantenha a operação simples e use constraints no template público.
