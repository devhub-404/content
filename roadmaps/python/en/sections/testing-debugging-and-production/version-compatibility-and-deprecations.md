# Python Versions, Compatibility, and Deprecations

Python releases add language features, standard-library APIs, optimizations, deprecations, and removals. A project should state its minimum supported Python version and test that floor, not merely the newest interpreter used by developers.

```python
import sys

if sys.version_info < (3, 14):
    raise RuntimeError("Python 3.14+ required")
```

Libraries often support several minor versions and use conditional imports or backports where needed. Applications can usually move faster, but dependencies and deployment images still need compatible wheels and runtime support.
