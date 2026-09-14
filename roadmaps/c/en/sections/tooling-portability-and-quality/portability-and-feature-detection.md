# Portability and Feature Detection

Portable C distinguishes the language standard from compiler extensions, operating-system APIs, CPU assumptions, and ABI details. Feature-test macros and configuration checks should guard optional capabilities rather than guessing from a compiler brand or platform name alone.

```c
#if __STDC_VERSION__ >= 202311L
    /* C23-capable language mode */
#endif
```

Keep platform-specific code behind narrow interfaces and build the portable core under strict standard modes when possible. Test integer widths, endianness, alignments, filesystem behavior, threading availability, and library contracts wherever your application actually depends on them.
