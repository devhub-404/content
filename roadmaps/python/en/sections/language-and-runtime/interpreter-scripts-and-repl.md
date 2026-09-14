# Interpreter, Scripts, and the REPL

Python can run source files directly, execute modules with `python -m`, evaluate code interactively, and expose rich introspection in the REPL. A module receives a `__name__`; when a file is the entry script its name is `"__main__"`.

```python
# app.py

def main() -> None:
    print("running")

if __name__ == "__main__":
    main()
```

Keep reusable behavior in functions and modules instead of putting the entire application at import time. The `if __name__ == "__main__"` guard keeps entry behavior separate from import behavior and makes code easier to test and reuse.
