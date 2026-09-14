# The `table` Library

The `table` library contains common operations for sequence-like tables, including sorting, insertion, removal, moving ranges, packing/unpacking, concatenation, and in Lua 5.5 preallocated creation with `table.create`. These functions assume the table shape required by each operation.

```lua
local values = {3, 1, 2}

table.sort(values)
table.insert(values, 4)

print(table.concat(values, ", "))

local last = table.remove(values)
print(last)
```

Sorting uses a comparator when the default ordering is not enough; that comparator must define a consistent order. Repeated insertion or removal in the middle of a large sequence shifts elements, so if performance matters choose a data representation based on actual operations instead of treating every table as the same abstract container.
