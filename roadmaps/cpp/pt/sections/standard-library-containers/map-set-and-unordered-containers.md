# Containers Associativos e Unordered

Containers associativos ordenados como `map` e `set` organizam chaves por uma relação de ordenação, geralmente com garantias tree-like. Unordered containers usam hashing e igualdade.

```cpp
std::map<std::string, int> ordered;
ordered["alice"] = 10;

std::unordered_map<std::string, int> fast;
fast["bob"] = 20;

std::set<int> unique{1, 2, 3};
```

Escolha ordered quando traversal ordenado ou queries de range importam; unordered quando lookup hash-based sem ordem basta. Qualidade do hash, estabilidade da chave, invalidation e worst-case fazem parte do contrato.
