# `vector`, `array` e `deque`

`std::vector` é a sequência dinâmica contígua default para muitos casos, `std::array` envolve array fixo com semântica de container e `std::deque` cresce eficientemente nas duas pontas sem uma única alocação contígua.

```cpp
std::vector<int> values{1, 2, 3};
values.push_back(4);

std::array<int, 3> fixed{1, 2, 3};

std::deque<int> queue;
queue.push_front(1);
queue.push_back(2);
```

Escolha conforme operações, invalidation, necessidade de contiguidade e comportamento de size. Crescimento de vector pode invalidar references/iterators. Reserve capacity quando conhece size aproximado, sem transformar tudo em micro-otimização prematura.
