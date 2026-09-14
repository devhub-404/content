# Filesystem

`std::filesystem` models paths, directories, file status, iteration, copying, renaming, and related filesystem operations with portable C++ interfaces. A `path` represents a filesystem path according to the platform's native conventions rather than merely an arbitrary UTF-8 string.

```cpp
namespace fs = std::filesystem;

for (const auto &entry :
     fs::directory_iterator(".")) {
    std::cout << entry.path() << '
';
}
```

Filesystem operations can fail because of permissions, races, missing entries, or platform differences. APIs offer throwing and `std::error_code` forms. Do not assume that a successful check guarantees a later operation; filesystem state can change between calls.
