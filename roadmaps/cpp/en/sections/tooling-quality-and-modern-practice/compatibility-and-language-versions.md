# Language Versions and Compatibility

C++ evolves in regular standard revisions, but compiler and standard-library support arrives feature by feature. A project should define a minimum language/library baseline and verify the exact facilities it uses rather than assuming one `-std=` flag makes every feature available everywhere.

```cpp
#if __cplusplus >= 202302L
    // C++23 language mode or later
#endif
```

Feature-test macros can guard optional facilities more precisely than compiler-version checks. Keep platform-specific code behind narrow boundaries and test supported compilers in CI. The current working draft contains future-standard features that should not be treated as portable stable C++ until your support baseline includes them.
