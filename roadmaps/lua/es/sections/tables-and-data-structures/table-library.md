# La Library `table`

La library `table` contiene operaciones comunes para tables tipo sequence, incluidos sort, insert, remove, move, pack/unpack, concat y, en Lua 5.5, creación preasignada con `table.create`. Cada función supone la forma de table indicada por su contrato.

```lua
local values = {3, 1, 2}

table.sort(values)
table.insert(values, 4)

print(table.concat(values, ", "))

local last = table.remove(values)
print(last)
```

Sorting puede recibir un comparator y este debe definir un orden consistente. Insert/remove repetidos en medio de una sequence grande desplazan elementos, así que elige la representación según las operaciones reales cuando importe el performance.
