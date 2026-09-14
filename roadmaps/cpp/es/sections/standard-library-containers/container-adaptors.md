# Adaptadores `stack`, `queue` y `priority_queue`

Los container adaptors exponen una interfaz restringida sobre un container subyacente para modelar stack, FIFO queue o priority queue. La restricción deja clara la semántica del algoritmo y evita operaciones aleatorias no relacionadas.

```cpp
std::queue<task> pending;
pending.push(task{});

std::priority_queue<int> priorities;
priorities.push(10);
priorities.push(5);
```

Usa un adaptor cuando su disciplina de acceso coincida con el algoritmo. `priority_queue` expone el máximo según el comparator, pero no ofrece iteración ordenada. Si necesitas eliminación arbitraria o recorrido estable, otro container puede encajar mejor.
