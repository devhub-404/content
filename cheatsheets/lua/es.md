---
locale: es
status: published
title: "Lua"
slug: lua
description: "Una referencia rápida orientada a tareas para sintaxis, APIs y workflows cotidianos de Lua."
tags:
  - lua
  - cheatsheet
  - quick-reference
references:
  - label: "Lua 5.5 Reference Manual"
    url: https://www.lua.org/manual/5.5/manual.html
  - label: "Lua 5.5 Read Me"
    url: https://www.lua.org/manual/5.5/readme.html
  - label: "Lua Documentation"
    url: https://www.lua.org/docs.html
---

# Lua

Referencia rápida orientada a tareas. Busca en la página y copia el ejemplo más pequeño que corresponda a lo que necesitas.

## Lenguaje y Runtime

**Qué es Lua**

```lua
print("Hello, Lua")
```

**Chunks y el Intérprete Standalone**

```lua
-- hello.lua
local name = arg[1] or "world"
print("Hello, " .. name)
```

**`load`, `loadfile` y Chunks Dinámicos**

```lua
local fn, err = load("return 20 + 22")

if not fn then
    error(err)
end

print(fn())
```

**Lua como Lenguaje Embebido**

```lua
-- The host may expose a small API:
local player = game.current_player()
player:set_score(player:score() + 10)
```

## Valores, Variables y Expresiones

**Tipos, `nil` y Truthiness**

```lua
local values = {
    type(nil),
    type(true),
    type(42),
    type("lua"),
    type({}),
    type(function() end),
}

for _, value in ipairs(values) do
    print(value)
end
```

**Locals, Globals y Scope Léxico**

```lua
local count = 10

do
    local count = 20
    print(count) -- 20
end

print(count) -- 10
```

**Números y Operadores**

```lua
local integer = 7
local float = 7.5

print(integer + 2)
print(float / 2)
print(7 // 2)
print(2 ^ 8)
print(0xff)
```

**Strings, Concatenación y Conversión**

```lua
local language = "Lua"
local version = 5.5

local label = language .. " " .. tostring(version)
print(label)
print(#label)
```

## Tables y Estructuras de Datos

**Constructors de Table y Fields**

```lua
local user = {
    id = 42,
    name = "Mina",
    active = true,
}

print(user.name)
print(user["id"])
```

**Sequences, Claves Enteras y Length**

```lua
local colors = {"red", "green", "blue"}

print(colors[1])
print(#colors)

colors[#colors + 1] = "gold"
```

**`next`, `pairs` e `ipairs`**

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

**La Library `table`**

```lua
local values = {3, 1, 2}

table.sort(values)
table.insert(values, 4)

print(table.concat(values, ", "))

local last = table.remove(values)
print(last)
```

## Flujo de Control y Functions

**`if`, `while`, `repeat` y `for`**

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

**Functions y Múltiples Resultados**

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

**Varargs y Named Vararg Tables**

```lua
local function describe(prefix, ... args)
    print(prefix, args.n)

    for i = 1, args.n do
        print(i, args[i])
    end
end

describe("values", 10, 20, nil)
```

**Closures y Upvalues**

```lua
local function counter()
    local value = 0

    return function()
        value = value + 1
        return value
    end
end

local next_value = counter()
print(next_value())
print(next_value())
```

## Modules y Environments

**`require` y Modules**

```lua
-- greeting.lua
local M = {}

function M.hello(name)
    return "Hello, " .. name
end

return M
```

**`package.path`, `package.cpath` y Searchers**

```lua
print(package.path)
print(package.cpath)

local json = require("json")
```

**Environments y `_ENV`**

```lua
local env = {
    print = print,
    answer = 42,
}

local fn = assert(load(
    "print(answer)",
    "example",
    "t",
    env
))

fn()
```

**Estado de Module y Dependency Injection**

```lua
local function new_service(clock)
    local service = {}

    function service.now()
        return clock()
    end

    return service
end

return new_service
```

## Metatables y Modelos de Objetos

**Metatables y Metamethods**

```lua
local point_mt = {}

function point_mt.__tostring(p)
    return ("(%d, %d)"):format(p.x, p.y)
end

local p = setmetatable({x = 3, y = 4}, point_mt)
print(p)
```

**`__index` y Objetos Prototype-style**

```lua
local Account = {}
Account.__index = Account

function Account.new(balance)
    return setmetatable({
        balance = balance or 0
    }, Account)
end

function Account:deposit(amount)
    self.balance = self.balance + amount
end
```

**Metamethods de Operadores y Llamada**

```lua
local vector_mt = {}

function vector_mt.__add(a, b)
    return setmetatable({
        x = a.x + b.x,
        y = a.y + b.y,
    }, vector_mt)
end

local a = setmetatable({x = 1, y = 2}, vector_mt)
local b = setmetatable({x = 3, y = 4}, vector_mt)

local c = a + b
```

**Userdata y Objetos del Host**

```lua
-- From Lua, host userdata can look like this:
local file = host.open_file("report.txt")
file:write("hello")
file:close()
```

## Coroutines, Errores y Recursos

**Errors, `pcall` y `xpcall`**

```lua
local function parse()
    error("invalid input")
end

local ok, err = pcall(parse)

if not ok then
    print("failed:", err)
end
```

**Coroutines: Create, Resume y Yield**

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

**`coroutine.wrap` e Iterators Basados en Coroutine**

```lua
local function values()
    return coroutine.wrap(function()
        coroutine.yield("a")
        coroutine.yield("b")
        coroutine.yield("c")
    end)
end

local next_value = values()
print(next_value())
print(next_value())
```

**Variables To-be-closed y Cleanup de Recursos**

```lua
local file <close> = assert(io.open("report.txt", "w"))
file:write("hello
")
-- file is closed when the scope ends
```

## Memoria y Garbage Collection

**Modelo de Garbage Collection**

```lua
local data = {}

for i = 1, 1000 do
    data[i] = {value = i}
end

data = nil
collectgarbage("collect")
```

**Weak Tables**

```lua
local cache = setmetatable({}, {
    __mode = "v"
})

local object = {name = "temporary"}
cache.key = object

object = nil
collectgarbage()
```

**Finalizers y `__gc`**

```lua
local mt = {
    __gc = function(object)
        print("finalizing", object.name)
    end
}

local object = setmetatable({
    name = "resource"
}, mt)
```

**Asignación y Lua Consciente de Memoria**

```lua
local items = table.create(1000, 0)

for i = 1, 1000 do
    items[i] = i * 2
end
```

## Bibliotecas Estándar

**Library de String y Lua Patterns**

```lua
local text = "user:42"

local name, id = text:match("^(%a+):(%d+)$")

print(name, id)

local cleaned = text:gsub("%d+", "<id>")
print(cleaned)
```

**Library UTF-8**

```lua
local text = "Olá, 世界"

print(utf8.len(text))

for position, codepoint in utf8.codes(text) do
    print(position, codepoint)
end
```

**I/O y Archivos**

```lua
local file <close> = assert(io.open("data.txt", "w"))
file:write("alpha
")
file:write("beta
")
file:flush()
```

**`math`, `os` y Basic Library**

```lua
math.randomseed(1234)

print(math.sqrt(81))
print(math.random(1, 6))
print(os.date("%Y-%m-%d"))

local value = tonumber("42")
assert(value == 42)
```

## C API, Debugging y Producción

**Modelo de Stack de la C API**

```lua
-- Conceptual Lua side:
local result = native.add(20, 22)
print(result)
```

**Registrando Functions Nativas y Userdata**

```lua
-- After the host registers a library:
local socket = net.connect("example.com", 443)

socket:send("hello")
socket:close()
```

**Debug Library, Hooks y Tracebacks**

```lua
local function work()
    error("boom")
end

local ok, err = xpcall(work, debug.traceback)

if not ok then
    print(err)
end
```
