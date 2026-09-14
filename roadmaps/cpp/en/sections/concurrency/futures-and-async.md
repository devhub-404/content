# Futures and `std::async`

`std::future` represents a result that becomes available later and can receive values from promises, packaged tasks, or `std::async`. `get()` waits and either returns the result or rethrows the stored exception.

```cpp
auto future = std::async(
    std::launch::async,
    [] { return expensive_work(); }
);

auto result = future.get();
```

`std::async` has launch-policy semantics that can be surprising if left implicit, and futures are a relatively low-level building block compared with richer executors/task systems outside the current stable standard. Use them when their ownership and waiting model fits the task clearly.
