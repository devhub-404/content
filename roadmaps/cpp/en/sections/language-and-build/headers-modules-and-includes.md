# Headers, Modules, and Includes

Headers remain the dominant way to share declarations, while C++20 modules provide a language-level mechanism for named module interfaces and imports. Modules can reduce textual inclusion and some macro/name-leakage problems, but build-system and compiler support still influence how practical they are in a project.

```cpp
// geometry.cppm
export module geometry;

export struct point {
    double x;
    double y;
};

export double length(point p);
```

Do not treat modules as a simple search-and-replace for headers. A project needs a coherent module build graph, and third-party dependencies may still be header-based. For headers, use reliable include guards or `#pragma once` where your toolchain supports it and make each header self-sufficient.
