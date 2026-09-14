# `vector`, `array` y `deque`

`std::vector` es la secuencia dinámica contigua por defecto en muchos casos, `std::array` envuelve un array fijo con semántica de container y `std::deque` crece eficientemente en ambos extremos sin una única asignación contigua.

```cpp
std::vector<int> values{1, 2, 3};
values.push_back(4);

std::array<int, 3> fixed{1, 2, 3};

std::deque<int> queue;
queue.push_front(1);
queue.push_back(2);
```

Elige según operaciones, invalidation, necesidad de contigüidad y comportamiento de tamaño. El crecimiento de vector puede invalidar references/iterators. Reserva capacity si conoces el tamaño aproximado, sin convertir cada decisión en micro-optimización prematura.
