# Debugging Native C++

Native debuggers can inspect stack frames, variables, object memory, exceptions, threads, and core dumps. Build with debug symbols and understand that optimization can reorder or eliminate source-level variables, making highly optimized debugging look different from the source.

```cpp
std::vector<int> values{1, 2, 3};
std::cout << values.at(10) << '
';
```

When the crash site looks innocent, investigate earlier lifetime errors, iterator invalidation, buffer corruption, data races, or moved-from misuse. Sanitizers and minimized reproducers complement a debugger. Preserve exact binaries and symbols when diagnosing production native crashes.
