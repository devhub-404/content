# Headers and `#include`

Headers normally contain declarations, type definitions, macros, and inline definitions that multiple translation units need to share. `#include` is textual preprocessing: the included tokens become part of the current translation unit before C compilation proper.

```c
// point.h
#ifndef POINT_H
#define POINT_H

struct point {
    double x;
    double y;
};

double distance_from_origin(struct point p);

#endif
```

Use include guards or another supported once-only mechanism so a header can be included repeatedly without duplicate definitions. A header should include the dependencies required for its own declarations instead of relying on an accidental include order in the consuming source file.
