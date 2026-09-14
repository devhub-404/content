# `auto`, `decltype`, and Type Deduction

`auto` asks the compiler to deduce a declared type from an initializer according to template-like deduction rules. References and top-level constness are not always preserved unless you write them explicitly. `decltype` queries the type of an expression with rules that depend on the expression form.

```cpp
const int count = 42;
auto a = count;          // int
auto &b = count;         // const int&
decltype(count) c = 7;   // const int
```

Type deduction is most valuable when the type is obvious from the right-hand side, verbose because of templates, or intentionally generic. Avoid `auto` where the exact type communicates a critical unit, ownership boundary, or expensive conversion that would otherwise be hidden.
