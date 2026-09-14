# Virtual Environments and Installation

A virtual environment gives a project an isolated interpreter environment and package-installation location, preventing unrelated projects from sharing one mutable global dependency set. `venv` is built into Python; package installation is commonly handled through pip and higher-level tools.

```python
# Typical workflow:
# python -m venv .venv
# . .venv/bin/activate
# python -m pip install -U pip
# python -m pip install package-name
```

Treat the environment definition as project data: pin or constrain dependencies according to your deployment policy and reproduce installs in CI. Activating a venv is shell convenience; invoking its Python executable directly is equally valid.
