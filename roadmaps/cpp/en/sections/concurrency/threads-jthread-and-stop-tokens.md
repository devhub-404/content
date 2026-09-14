# Threads, `jthread`, and Stop Tokens

`std::thread` represents an execution thread and requires explicit joining or detaching. `std::jthread` adds automatic joining and integrates cooperative cancellation through stop tokens, making it a safer default for many scoped thread lifetimes.

```cpp
std::jthread worker([](std::stop_token stop) {
    while (!stop.stop_requested()) {
        do_one_unit();
    }
});
```

Thread cancellation is cooperative: the running code must check or wait on cancellation-aware operations. Design object lifetime so captured data outlives the thread, and prefer task-level abstractions when raw threads are lower-level than the problem requires.
