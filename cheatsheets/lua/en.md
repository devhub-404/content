---
locale: en
status: published
title: "Lua"
slug: lua
description: "A task-oriented quick reference for everyday Lua syntax, APIs, and workflows."
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

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## Language & Runtime

**What Lua Is**

```lua
print("Hello, Lua")
```

**Chunks and the Standalone Interpreter**

```lua
-- hello.lua
local name = arg[1] or "world"
print("Hello, " .. name)
```

**`load`, `loadfile`, and Dynamic Chunks**

```lua
local fn, err = load("return 20 + 22")

if not fn then
    error(err)
end

print(fn())
```

**Lua as an Embedded Language**

```lua
-- The host may expose a small API:
local player = game.current_player()
player:set_score(player:score() + 10)
```

## Values, Variables & Expressions

**Types, `nil`, and Truthiness**

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

**Locals, Globals, and Lexical Scope**

```lua
local count = 10

do
    local count = 20
    print(count) -- 20
end

print(count) -- 10
```

**Numbers and Operators**

```lua
local integer = 7
local float = 7.5

print(integer + 2)
print(float / 2)
print(7 // 2)
print(2 ^ 8)
print(0xff)
```

**Strings, Concatenation, and Conversion**

```lua
local language = "Lua"
local version = 5.5

local label = language .. " " .. tostring(version)
print(label)
print(#label)
```

## Tables & Data Structures

**Table Constructors and Fields**

```lua
local user = {
    id = 42,
    name = "Mina",
    active = true,
}

print(user.name)
print(user["id"])
```

**Sequences, Integer Keys, and Length**

```lua
local colors = {"red", "green", "blue"}

print(colors[1])
print(#colors)

colors[#colors + 1] = "gold"
```

**`next`, `pairs`, and `ipairs`**

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

**The `table` Library**

```lua
local values = {3, 1, 2}

table.sort(values)
table.insert(values, 4)

print(table.concat(values, ", "))

local last = table.remove(values)
print(last)
```

## Control Flow & Functions

**`if`, `while`, `repeat`, and `for`**

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

**Functions and Multiple Results**

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

**Varargs and Named Vararg Tables**

```lua
local function describe(prefix, ... args)
    print(prefix, args.n)

    for i = 1, args.n do
        print(i, args[i])
    end
end

describe("values", 10, 20, nil)
```

**Closures and Upvalues**

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

## Modules & Environments

**`require` and Modules**

```lua
-- greeting.lua
local M = {}

function M.hello(name)
    return "Hello, " .. name
end

return M
```

**`package.path`, `package.cpath`, and Searchers**

```lua
print(package.path)
print(package.cpath)

local json = require("json")
```

**Environments and `_ENV`**

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

**Module State and Dependency Injection**

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

## Metatables & Object Models

**Metatables and Metamethods**

```lua
local point_mt = {}

function point_mt.__tostring(p)
    return ("(%d, %d)"):format(p.x, p.y)
end

local p = setmetatable({x = 3, y = 4}, point_mt)
print(p)
```

**`__index` and Prototype-style Objects**

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

**Operator and Call Metamethods**

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

**Userdata and Host Objects**

```lua
-- From Lua, host userdata can look like this:
local file = host.open_file("report.txt")
file:write("hello")
file:close()
```

## Coroutines, Errors & Resources

**Errors, `pcall`, and `xpcall`**

```lua
local function parse()
    error("invalid input")
end

local ok, err = pcall(parse)

if not ok then
    print("failed:", err)
end
```

**Coroutines: Create, Resume, and Yield**

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

**`coroutine.wrap` and Coroutine-based Iterators**

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

**To-be-closed Variables and Resource Cleanup**

```lua
local file <close> = assert(io.open("report.txt", "w"))
file:write("hello
")
-- file is closed when the scope ends
```

## Memory & Garbage Collection

**Garbage Collection Model**

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

**Finalizers and `__gc`**

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

**Allocation and Memory-aware Lua**

```lua
local items = table.create(1000, 0)

for i = 1, 1000 do
    items[i] = i * 2
end
```

## Standard Libraries

**String Library and Lua Patterns**

```lua
local text = "user:42"

local name, id = text:match("^(%a+):(%d+)$")

print(name, id)

local cleaned = text:gsub("%d+", "<id>")
print(cleaned)
```

**UTF-8 Library**

```lua
local text = "Olá, 世界"

print(utf8.len(text))

for position, codepoint in utf8.codes(text) do
    print(position, codepoint)
end
```

**I/O and Files**

```lua
local file <close> = assert(io.open("data.txt", "w"))
file:write("alpha
")
file:write("beta
")
file:flush()
```

**`math`, `os`, and the Basic Library**

```lua
math.randomseed(1234)

print(math.sqrt(81))
print(math.random(1, 6))
print(os.date("%Y-%m-%d"))

local value = tonumber("42")
assert(value == 42)
```

## C API, Debugging & Production

**The C API Stack Model**

```lua
-- Conceptual Lua side:
local result = native.add(20, 22)
print(result)
```

**Registering Native Functions and Userdata**

```lua
-- After the host registers a library:
local socket = net.connect("example.com", 443)

socket:send("hello")
socket:close()
```

**Debug Library, Hooks, and Tracebacks**

```lua
local function work()
    error("boom")
end

local ok, err = xpcall(work, debug.traceback)

if not ok then
    print(err)
end
```
