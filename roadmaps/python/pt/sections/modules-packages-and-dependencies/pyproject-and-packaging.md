# `pyproject.toml` e Packaging

Packaging moderno usa `pyproject.toml` para metadata e build system. Backends produzem wheels/sdists e indexes distribuem artifacts. Apps e libraries têm políticas diferentes de pin/version.

```toml
[project]
name = "example"
version = "1.0.0"
requires-python = ">=3.14"
dependencies = ["httpx>=0.28,<1"]
```

Declare minimum Python/dependencies honestamente. Teste wheel/install real, não apenas source editable, pois package data/import layout podem falhar só após build.
