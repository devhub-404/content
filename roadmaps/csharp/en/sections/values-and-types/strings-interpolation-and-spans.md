# Strings, Interpolation, and Text Values

`string` is an immutable sequence of UTF-16 code units. Interpolated strings combine expressions with formatting, raw string literals simplify multiline or quote-heavy text, and `StringBuilder` is useful when building large mutable text repeatedly. Text indexing is not the same as user-perceived character segmentation.

```csharp
string name = "Mina";
string message = $"Hello, {name}!";
string raw = """
    line one
    line two
    """;

ReadOnlySpan<char> prefix = message.AsSpan(0, 5);
```

For performance-sensitive parsing, `Span<char>` and `ReadOnlySpan<char>` can view existing memory without allocating substrings. Use ordinary strings by default and introduce span-based APIs only when profiling or library contracts justify the extra lifetime restrictions.
