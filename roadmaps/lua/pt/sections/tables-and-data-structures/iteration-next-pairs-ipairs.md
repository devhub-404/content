# `next`, `pairs` e `ipairs`

`pairs` percorre key/value entries usando o comportamento de iteração da table, enquanto `ipairs` percorre chaves inteiras consecutivas desde 1 até a primeira ausente. `next` é a operação primitiva por trás do traversal comum.

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

A ordem de table iteration comum não é sorted nem contrato estável. Se a ordem importa, colete e ordene keys ou mantenha uma sequence separada. Evite mudanças estruturais durante traversal salvo quando as regras permitirem explicitamente.
