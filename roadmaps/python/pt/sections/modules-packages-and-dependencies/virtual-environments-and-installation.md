# Virtual Environments e Instalação

Virtual environment isola interpreter environment e package location, evitando dependencies globais compartilhadas. `venv` vem com Python e pip instala packages.

```python
# Typical workflow:
# python -m venv .venv
# . .venv/bin/activate
# python -m pip install -U pip
# python -m pip install package-name
```

Trate environment definition como dados do projeto: fixe/constranja dependencies conforme deploy e reproduza em CI. Activation é conveniência de shell.
