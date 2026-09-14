# Coroutines: Create, Resume y Yield

Las coroutines de Lua ofrecen suspensión y reanudación cooperativas. Una coroutine es un thread object de Lua con su propio stack. `resume` continúa, `yield` suspende y los valores pueden cruzar la frontera en ambas direcciones.

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

Las coroutines no son OS threads preemptivos. El código debe ceder control, por lo que son útiles para generators, state machines, schedulers cooperativos y async frameworks del host. Un error dentro de la coroutine aparece en el resultado de `resume`.
