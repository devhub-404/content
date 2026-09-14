# Specialization e Seleção de Overloads

Templates podem ser explicitamente specialized, parcialmente specialized em contextos como class templates, ou competir com overloads comuns. Esses mecanismos resolvem problemas diferentes e interagem com deduction/constraints.

```cpp
template <typename T>
void print(const T &value);

template <>
void print<bool>(const bool &value);

void print(const char *value);
```

Prefira overloads e concepts quando comportamento varia por capacidade reconhecível. Specialization explícita serve a implementação realmente excepcional, mas pode ficar difícil de descobrir quando espalhada pelo projeto.
