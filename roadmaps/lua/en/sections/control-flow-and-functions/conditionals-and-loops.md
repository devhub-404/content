# `if`, `while`, `repeat`, and `for`

Lua provides conventional conditional and loop statements: `if`, `while`, `repeat ... until`, numeric `for`, and generic `for`. Numeric `for` evaluates its bounds before the loop and in Lua 5.5 its control variables are read-only.

```lua
local total = 0

for i = 1, 5 do
    total = total + i
end

if total > 10 then
    print("large")
else
    print("small")
end
```

`repeat` checks its condition after executing the body, so it always runs at least once. `break` leaves a loop and `goto` can jump to a visible label when low-level control is genuinely clearer. Prefer structured loops and small functions over complicated jump graphs.
