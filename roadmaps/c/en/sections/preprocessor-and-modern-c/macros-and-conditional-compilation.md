# Macros and Conditional Compilation

The preprocessor performs token-level transformations before C compilation. Object-like and function-like macros can substitute tokens, and conditional directives select source according to macros or implementation conditions.

```c
#define ARRAY_COUNT(a) (sizeof(a) / sizeof((a)[0]))

#if defined(_WIN32)
    /* Windows-specific code */
#else
    /* portable/POSIX path */
#endif
```

Macros are not typed functions: arguments can be evaluated multiple times and precedence can change if parameters or results are not parenthesized carefully. Prefer ordinary functions, `static inline`, enums, or constants when they express the same job. Use conditional compilation to isolate true platform differences rather than fork ordinary logic everywhere.
