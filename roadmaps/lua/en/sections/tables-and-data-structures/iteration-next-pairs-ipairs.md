# `next`, `pairs`, and `ipairs`

`pairs` iterates key/value entries using the table's iteration behavior, while `ipairs` walks consecutive integer keys starting at 1 until the first absent entry. `next` is the primitive operation behind ordinary table traversal.

```lua
local user = {name = "Mina", score = 10}

for key, value in pairs(user) do
    print(key, value)
end

local colors = {"red", "green"}

for index, value in ipairs(colors) do
    print(index, value)
end
```

The order from ordinary hash-style table iteration is not a sorted or stable contract. If output order matters, collect the keys and sort them or maintain an ordered sequence separately. Avoid changing a table structurally during traversal unless the operation is explicitly permitted by the iteration rules.
