# `pyproject.toml` and Packaging

Modern Python packaging uses `pyproject.toml` for project metadata and build-system configuration. Build backends produce wheels and source distributions, while package indexes distribute artifacts. Applications and libraries have different version-pinning and publication needs.

```toml
[project]
name = "example"
version = "1.0.0"
requires-python = ">=3.14"
dependencies = ["httpx>=0.28,<1"]
```

Declare the Python-version floor and dependencies honestly. Test the wheel or installed project, not only an editable source checkout, because missing package data, import layout mistakes, and build metadata often appear only after packaging.
