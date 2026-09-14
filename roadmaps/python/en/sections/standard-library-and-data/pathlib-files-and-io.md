# `pathlib`, Files, and I/O

`pathlib.Path` provides object-oriented filesystem paths, while `open`, `io`, and higher-level helpers handle text and binary streams. Convenience methods are excellent for bounded files; streaming is better for large content.

```python
from pathlib import Path

path = Path("data") / "report.txt"
text = path.read_text(encoding="utf-8")
path.write_text(text + "
updated", encoding="utf-8")
```

Always specify text encoding at external boundaries unless a deliberate locale-dependent default is part of the contract. Filesystems can change between checks and operations, so handle the operation itself as fallible.
