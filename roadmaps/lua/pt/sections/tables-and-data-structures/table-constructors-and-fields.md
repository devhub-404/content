# Constructors de Table e Fields

Tables são a única estrutura de dados geral built-in de Lua. Chaves podem ser quase qualquer valor exceto nil e NaN, e valores podem ter qualquer tipo. `t.name` é shorthand para `t["name"]`, então objetos record-like são tables comuns com string keys.

```lua
local user = {
    id = 42,
    name = "Mina",
    active = true,
}

print(user.name)
print(user["id"])
```

Atribuir `nil` remove a entrada. Table possui identidade: atribuir uma table a outra variável não copia conteúdo. Decida quando partes do programa devem compartilhar a mesma table e quando uma cópia independente é necessária.
