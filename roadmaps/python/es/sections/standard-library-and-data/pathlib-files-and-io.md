# `pathlib`, Files e I/O

`pathlib.Path` ofrece filesystem paths orientados a objetos y `open`/`io` manejan streams. Los convenience methods sirven para archivos bounded; streaming para contenido grande.

```python
from pathlib import Path

path = Path("data") / "report.txt"
text = path.read_text(encoding="utf-8")
path.write_text(text + "
updated", encoding="utf-8")
```

Especifica encoding en boundaries de texto. El filesystem puede cambiar entre un check y la operación, así que trata la operación como fallible.
