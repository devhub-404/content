# Formas de Inicialização

C++ possui várias sintaxes de inicialização com regras diferentes de overload resolution e narrowing. Brace initialization é útil porque rejeita várias conversões narrowing e também inicializa aggregates e tipos compatíveis com `std::initializer_list`.

```cpp
int a = 10;
int b(20);
int c{30};

std::vector<int> values{1, 2, 3};
```

Não assuma que braces equivalem sempre a parênteses: a escolha de constructor pode mudar quando há initializer-list constructors. Use estilo consistente e entenda a API, especialmente containers onde `{10, 20}` pode significar dois elementos, não size/value.
