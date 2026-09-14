# Boolean, Character, and String Literals

C23 has the keywords `bool`, `true`, and `false` directly in the language. Character constants and string literals have encoding rules that depend on their prefix and the execution character set. An ordinary string literal is an array containing its characters followed by a terminating zero byte.

```c
bool ready = true;
char newline = '
';
const char *message = "hello";
```

A pointer to a string literal should be treated as pointing to immutable data; attempting to modify the literal is undefined behavior. `char` is a small integer type and its signedness is implementation-defined, so use `signed char`, `unsigned char`, or fixed-width integer types when the sign or byte semantics matter.
