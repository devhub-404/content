# Designing Maintainable C APIs

Maintainable C APIs make ownership, lifetime, mutability, buffer sizes, and error reporting explicit. Opaque structs can hide implementation details while exposing a stable pointer-based handle. Functions should state whether pointers may be null and whether memory is borrowed or transferred.

```c
struct parser;

struct parser *parser_create(void);
int parser_feed(struct parser *, const void *, size_t);
void parser_destroy(struct parser *);
```

Prefer small orthogonal operations over giant functions controlled by many flags, and pair constructors/acquirers with destructors/releasers. Version public structs carefully because their size and layout can become ABI. A good C API reduces the number of unwritten rules a caller must remember.
