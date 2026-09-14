# Adaptadores `stack`, `queue` e `priority_queue`

Container adaptors expõem interface restrita sobre um container subjacente para modelar stack, FIFO queue ou priority queue. A limitação deixa a semântica do algoritmo clara e impede operações aleatórias sem relação.

```cpp
std::queue<task> pending;
pending.push(task{});

std::priority_queue<int> priorities;
priorities.push(10);
priorities.push(5);
```

Use adaptor quando a disciplina de acesso corresponder ao algoritmo. `priority_queue` expõe o maior conforme comparator, mas não oferece iteração ordenada. Se precisa remoção arbitrária ou traversal estável, outro container pode ser melhor.
