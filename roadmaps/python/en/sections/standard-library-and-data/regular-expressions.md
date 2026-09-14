# Regular Expressions

The `re` module supports compiled patterns, groups, substitutions, flags, lookarounds, and Unicode-aware matching behavior. Raw strings are commonly used for patterns because they reduce collisions between Python string escaping and regular-expression escaping.

```python
import re

match = re.fullmatch(r"user-(\d+)", "user-42")
if match:
    user_id = int(match.group(1))
```

Regex is excellent for lexical patterns but can become unreadable for nested structured grammars. Prefer string methods for simple rules and dedicated parsers for formats whose grammar or error reporting matters.
