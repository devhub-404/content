# Constructors de Table y Fields

Las tables son la única estructura de datos general built-in de Lua. Las claves pueden ser casi cualquier valor salvo nil y NaN, y los valores pueden tener cualquier tipo. `t.name` es shorthand para `t["name"]`, así que los objetos tipo record son tables normales con claves string.

```lua
local user = {
    id = 42,
    name = "Mina",
    active = true,
}

print(user.name)
print(user["id"])
```

Asignar `nil` elimina la entrada. Una table tiene identidad: asignarla a otra variable no copia su contenido. Decide cuándo varias partes del programa deben compartir la misma table y cuándo necesitas una copia independiente.
