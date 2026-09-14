# Invalidation de Iterators e References

Containers padrão definem quando inserções, erases, rehash ou reallocation invalidam iterators, pointers e references. As regras variam bastante entre vector-like, node-based e unordered containers.

```cpp
std::vector<int> values{1, 2, 3};
auto it = values.begin();

values.push_back(4);
// 'it' may now be invalid if reallocation occurred.
```

Usar iterator invalidado é undefined behavior. Antes de armazenar iterators/references long-lived, entenda as mutações possíveis. Muitas vezes guardar uma chave/índice e fazer lookup novamente é mais seguro.
