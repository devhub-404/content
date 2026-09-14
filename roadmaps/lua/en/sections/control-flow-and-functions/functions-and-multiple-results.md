# Functions and Multiple Results

Functions are first-class values and can return several results. Multiple assignment receives those results positionally, filling missing positions with nil and discarding extra results when necessary. This makes result-plus-error and iterator protocols lightweight.

```lua
local function divide(a, b)
    if b == 0 then
        return nil, "division by zero"
    end

    return a / b
end

local value, err = divide(10, 2)
print(value, err)
```

The position of a multi-result expression matters: in many expression lists only its final position can expand to several values. Learn this rule before building helpers around `return`, function calls, constructors, and varargs, because adding parentheses or moving an expression can deliberately collapse it to one result.
