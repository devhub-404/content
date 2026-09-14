# Coroutines: Create, Resume e Yield

Coroutines Lua fornecem suspensão e retomada cooperativas. Uma coroutine é um thread object Lua com stack própria. `resume` continua, `yield` suspende e valores podem atravessar a fronteira nos dois sentidos.

```lua
local co = coroutine.create(function()
    for i = 1, 3 do
        coroutine.yield(i)
    end
end)

while coroutine.status(co) ~= "dead" do
    local ok, value = coroutine.resume(co)
    if ok and value then
        print(value)
    end
end
```

Coroutines não são OS threads preemptivas. O código precisa ceder controle, sendo útil em generators, state machines, schedulers cooperativos e async frameworks de hosts. Error dentro de coroutine aparece no resultado de `resume`.
