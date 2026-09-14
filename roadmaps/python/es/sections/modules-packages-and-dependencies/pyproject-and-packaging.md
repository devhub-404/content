# `pyproject.toml` y Packaging

El packaging moderno usa `pyproject.toml` para metadata y build system. Los backends producen wheels/sdists y los indexes distribuyen artifacts. Apps y libraries tienen políticas distintas de pin/version.

```toml
[project]
name = "example"
version = "1.0.0"
requires-python = ">=3.14"
dependencies = ["httpx>=0.28,<1"]
```

Declara el mínimo de Python/dependencies honestamente. Prueba el wheel/install real, no solo source editable, porque package data/import layout pueden fallar solo tras el build.
