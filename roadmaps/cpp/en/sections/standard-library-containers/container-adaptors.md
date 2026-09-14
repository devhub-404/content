# Container Adaptors: `stack`, `queue`, and `priority_queue`

Container adaptors expose a restricted interface over an underlying container to model a stack, FIFO queue, or priority queue. The restricted operations make the intended data-structure semantics clear and prevent unrelated random-access operations.

```cpp
std::queue<task> pending;
pending.push(task{});

std::priority_queue<int> priorities;
priorities.push(10);
priorities.push(5);
```

Use an adaptor when its access discipline matches the algorithm. A priority queue exposes the highest-priority element according to its comparator but does not provide sorted iteration. If the algorithm needs arbitrary removal or stable ordered traversal, another container may fit better.
