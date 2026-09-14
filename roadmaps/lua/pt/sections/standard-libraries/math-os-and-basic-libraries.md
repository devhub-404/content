# `math`, `os` e Basic Library

Basic library contém helpers como `assert`, `error`, `type`, conversion, loading, metatable operations e protected calls. `math` fornece funções numéricas/pseudo-random e `os` recursos selecionados de process, clock, date, locale, environment e filesystem.

```lua
math.randomseed(1234)

print(math.sqrt(81))
print(math.random(1, 6))
print(os.date("%Y-%m-%d"))

local value = tonumber("42")
assert(value == 42)
```

Essas libraries são capabilities, principalmente em runtime embedded/sandboxed. O host pode não abrir todas. Random comum não é automaticamente criptográfico e funções de OS não devem ser expostas a scripts não confiáveis sem decisão explícita de segurança.
