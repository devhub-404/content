# Virtual Environments e Instalación

Un virtual environment aísla el interpreter environment y la ubicación de packages, evitando dependencies globales compartidas. `venv` viene con Python y pip instala packages.

```python
# Typical workflow:
# python -m venv .venv
# . .venv/bin/activate
# python -m pip install -U pip
# python -m pip install package-name
```

Trata la definición del environment como datos del proyecto: fija/restringe dependencies según despliegue y reproduce en CI. La activación es comodidad del shell.
