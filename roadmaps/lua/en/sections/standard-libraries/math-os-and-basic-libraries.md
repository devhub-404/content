# `math`, `os`, and the Basic Library

The basic library contains core helpers such as `assert`, `error`, `type`, conversion, loading, metatable operations, and protected calls. `math` provides numeric functions and pseudo-random facilities, while `os` exposes selected process, clock, date, locale, environment, and filesystem-related operations.

```lua
math.randomseed(1234)

print(math.sqrt(81))
print(math.random(1, 6))
print(os.date("%Y-%m-%d"))

local value = tonumber("42")
assert(value == 42)
```

These libraries are capabilities, especially in an embedded or sandboxed runtime. A host may not open all standard libraries. Random facilities are not automatically cryptographically secure, and operating-system functions should not be exposed to untrusted scripts unless that access is intentionally part of the host's security model.
