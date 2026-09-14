# Interpreter, Scripts y REPL

Python puede ejecutar source files, modules con `python -m` y código interactivo. Un module recibe `__name__`; cuando es el entry script, el nombre es `"__main__"`.

```python
# app.py

def main() -> None:
    print("running")

if __name__ == "__main__":
    main()
```

Mantén comportamiento reutilizable en functions/modules en vez de ejecutar todo al importar. El guard `if __name__ == "__main__"` separa entry behavior de import y facilita tests.
