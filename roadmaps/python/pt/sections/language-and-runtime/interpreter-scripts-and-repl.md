# Interpreter, Scripts e REPL

Python pode executar source files, modules com `python -m` e código interativo. Um module recebe `__name__`; quando é o entry script, o nome é `"__main__"`.

```python
# app.py

def main() -> None:
    print("running")

if __name__ == "__main__":
    main()
```

Mantenha comportamento reutilizável em funções/modules em vez de executar tudo no import. O guard `if __name__ == "__main__"` separa entry behavior de import e facilita testes.
