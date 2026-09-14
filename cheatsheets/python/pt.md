---
locale: pt
status: published
title: "Python"
slug: python
description: "Uma referência rápida orientada a tarefas para sintaxe, APIs e workflows cotidianos de Python."
tags:
  - python
  - cheatsheet
  - quick-reference
references:
  - label: "Python 3.14 Tutorial"
    url: https://docs.python.org/3.14/tutorial/
  - label: "Python 3.14 Standard Library"
    url: https://docs.python.org/3.14/library/
  - label: "Python Data Model"
    url: https://docs.python.org/3.14/reference/datamodel.html
---

# Python

Referência rápida orientada a tarefas. Pesquise na página e copie o menor exemplo que corresponde ao que você precisa.

## Linguagem e Runtime

**Interpreter, Scripts e REPL**

```python
# app.py

def main() -> None:
    print("running")

if __name__ == "__main__":
    main()
```

**Nomes, Objetos e Assignment**

```python
items = [1, 2, 3]
alias = items
alias.append(4)

print(items)  # [1, 2, 3, 4]
```

**Indentação, Statements e Expressions**

```python
value = 10

if value > 0:
    label = "positive"
else:
    label = "non-positive"

result = value * 2
```

## Valores e Tipos de Dados

**Números, Booleanos e `None`**

```python
count = 42
ratio = 0.75
price = 19.99
ready = True
missing = None
```

**Strings, Bytes e Texto**

```python
name = "Mina"
message = f"Hello, {name}!"
raw = r"C:\temp\file.txt"

data = "Olá".encode("utf-8")
text = data.decode("utf-8")
```

**Lists, Tuples e Sequences**

```python
values = [10, 20, 30]
values.append(40)

point = (3, 4)
x, y = point
```

**Dictionaries e Sets**

```python
counts = {"ready": 2, "failed": 1}
counts["ready"] += 1

seen = {"python", "typing"}
seen.add("asyncio")
```

**Mutability, Cópias e Hashability**

```python
import copy

original = [[1, 2], [3, 4]]
shallow = original.copy()
deep = copy.deepcopy(original)
```

## Fluxo de Controle e Patterns

**Truthiness, `if` e Conditional Expressions**

```python
label = "ready" if ready else "waiting"

if items:
    print("has items")
elif fallback is not None:
    print(fallback)
```

**`for`, `while`, `break` e `else` de Loop**

```python
for item in items:
    if matches(item):
        found = item
        break
else:
    found = None
```

**Structural Pattern Matching**

```python
match message:
    case {"type": "user", "id": int(user_id)}:
        handle_user(user_id)
    case ["move", x, y]:
        move(x, y)
    case _:
        ignore()
```

## Funções, Escopos e Closures

**Funções, Parâmetros e Retornos**

```python
def connect(host: str, port: int = 443) -> str:
    return f"{host}:{port}"

address = connect("example.com")
```

**Argumentos Positional, Keyword e Variadic**

```python
def request(url, /, method="GET", *, timeout=5, **headers):
    ...

request("/users", timeout=2, Accept="application/json")
```

**Escopo, `global`, `nonlocal` e Closures**

```python
def make_counter():
    count = 0

    def next_value():
        nonlocal count
        count += 1
        return count

    return next_value
```

**Lambdas e Valores Callable**

```python
key = lambda user: user.name.casefold()
users.sort(key=key)

def apply(value, fn):
    return fn(value)
```

**Decorators**

```python
def trace(fn):
    def wrapper(*args, **kwargs):
        print(fn.__name__)
        return fn(*args, **kwargs)
    return wrapper

@trace
def work():
    pass
```

## Comprehensions, Iterators e Generators

**Comprehensions**

```python
squares = [x * x for x in values if x > 0]
lookup = {user.id: user for user in users}
unique = {name.casefold() for name in names}
```

**Protocolos Iterable e Iterator**

```python
iterator = iter(values)
while True:
    try:
        value = next(iterator)
    except StopIteration:
        break
    print(value)
```

**Generators e `yield`**

```python
def even_numbers(limit):
    for value in range(0, limit + 1, 2):
        yield value

for value in even_numbers(10):
    print(value)
```

**Delegação de Generator e `yield from`**

```python
def chain(*iterables):
    for iterable in iterables:
        yield from iterable
```

## Classes e Data Model

**Classes, Instances e Attributes**

```python
class Account:
    def __init__(self, owner: str) -> None:
        self.owner = owner
        self.balance = 0

    def deposit(self, amount: int) -> None:
        self.balance += amount
```

**Dataclasses**

```python
from dataclasses import dataclass

@dataclass(frozen=True, slots=True)
class User:
    id: int
    name: str
```

**Properties e Attributes Gerenciados**

```python
class Celsius:
    def __init__(self, value: float) -> None:
        self._value = value

    @property
    def value(self) -> float:
        return self._value
```

**Herança, `super` e MRO**

```python
class LoggingMixin:
    def save(self):
        print("saving")
        return super().save()

class Repository(LoggingMixin, BaseRepository):
    pass
```

**Dunder Methods e Protocols**

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __len__(self):
        return 2

    def __repr__(self):
        return f"Point({self.x!r}, {self.y!r})"
```

## Typing e Análise Estática

**Type Annotations e Static Checkers**

```python
def greet(name: str) -> str:
    return f"Hello, {name}"

count: int = 0
```

**Unions, Optionals e Narrowing**

```python
def length(value: str | None) -> int:
    if value is None:
        return 0
    return len(value)
```

**Generics, Type Variables e Protocols**

```python
from typing import Protocol, TypeVar

T = TypeVar("T")

class SizedName(Protocol):
    name: str

def first(values: list[T]) -> T:
    return values[0]
```

**`Any`, Casts e Validação Runtime**

```python
from typing import Any, cast

raw: Any = load_external()
name = cast(str, raw)  # static assertion only

if not isinstance(raw, str):
    raise TypeError("expected string")
```

## Modules, Packages e Dependências

**Modules, Imports e Import Time**

```python
# pricing.py
RATE = 0.20

def total(value: float) -> float:
    return value * (1 + RATE)

# app.py
from pricing import total
```

**Imports Absolutos, Relativos e Dinâmicos**

```python
from app.services import billing
from .models import User

import importlib
plugin = importlib.import_module("plugins.example")
```

**Virtual Environments e Instalação**

```python
# Typical workflow:
# python -m venv .venv
# . .venv/bin/activate
# python -m pip install -U pip
# python -m pip install package-name
```

**`pyproject.toml` e Packaging**

```toml
[project]
name = "example"
version = "1.0.0"
requires-python = ">=3.14"
dependencies = ["httpx>=0.28,<1"]
```

## Exceptions, Contextos e Recursos

**Exceptions e Blocos `try`**

```python
try:
    value = int(text)
except ValueError as exc:
    report(exc)
else:
    use(value)
finally:
    cleanup()
```

**Exceptions Customizadas**

```python
class InvalidOrderError(ValueError):
    pass

if total < 0:
    raise InvalidOrderError("total cannot be negative")
```

**Context Managers e `with`**

```python
with open(path, "r", encoding="utf-8") as file:
    text = file.read()
```

**Async Context Managers**

```python
async with session.get(url) as response:
    body = await response.text()
```

## Async e Concorrência

**`async`, `await` e Coroutines**

```python
async def load(url: str) -> bytes:
    response = await fetch(url)
    return response.body
```

**Tasks, Task Groups e Structured Concurrency**

```python
async with asyncio.TaskGroup() as group:
    user_task = group.create_task(load_user())
    order_task = group.create_task(load_orders())

user = user_task.result()
orders = order_task.result()
```

**Timeouts, Cancellation e Backpressure**

```python
async with asyncio.timeout(5):
    result = await service.load()

queue = asyncio.Queue(maxsize=100)
```

**Threads, Processes e GIL**

```python
from concurrent.futures import ThreadPoolExecutor

with ThreadPoolExecutor() as pool:
    results = list(pool.map(fetch, urls))
```

**Python Free-threaded**

```python
import sys

if hasattr(sys, "_is_gil_enabled"):
    print("GIL enabled:", sys._is_gil_enabled())
```

## Standard Library e Dados

**`pathlib`, Files e I/O**

```python
from pathlib import Path

path = Path("data") / "report.txt"
text = path.read_text(encoding="utf-8")
path.write_text(text + "
updated", encoding="utf-8")
```

**JSON, CSV e Dados Estruturados**

```python
import json

payload = json.loads(text)
name = payload["name"]

encoded = json.dumps({"name": name})
```

**Datas, Horas, Time Zones e Durations**

```python
from datetime import datetime, timezone
from zoneinfo import ZoneInfo

now = datetime.now(timezone.utc)
local = now.astimezone(ZoneInfo("America/Los_Angeles"))
```

**Expressões Regulares**

```python
import re

match = re.fullmatch(r"user-(\d+)", "user-42")
if match:
    user_id = int(match.group(1))
```

## Testes, Debugging e Produção

**Unit Testing e Ecossistema de Testes**

```python
import unittest

class CalculatorTest(unittest.TestCase):
    def test_add(self):
        self.assertEqual(add(2, 3), 5)
```

**Debugging, Logging e Tracebacks**

```python
import logging

logger = logging.getLogger(__name__)

try:
    process()
except Exception:
    logger.exception("processing failed")
    raise
```

**Profiling e Performance**

```python
import cProfile

cProfile.run("main()", "profile.stats")
```

**Style, Formatting e Linting**

```python
# Common project tools may include:
# ruff check .
# ruff format .
# python -m pytest
# pyright / mypy
```
