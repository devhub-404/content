# `pathlib`, Files e I/O

`pathlib.Path` fornece filesystem paths orientados a objeto, e `open`/`io` tratam streams. Convenience methods servem a arquivos bounded; streaming a conteúdo grande.

```python
from pathlib import Path

path = Path("data") / "report.txt"
text = path.read_text(encoding="utf-8")
path.write_text(text + "
updated", encoding="utf-8")
```

Especifique encoding em boundaries de texto. Filesystem pode mudar entre check e operação, então trate a operação como fallible.
