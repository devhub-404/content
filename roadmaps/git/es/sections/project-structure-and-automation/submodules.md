# Submodules y Repositorios Anidados

Un submodule registra un commit específico de otro repositorio en un path del superproject. El parent rastrea esa referencia/configuración, no todo el working state del repositorio anidado como archivos ordinarios.

```bash
git submodule add <repository-url> libs/example
git submodule update --init --recursive
git clone --recurse-submodules <repository-url>
```

Los submodules hacen explícito dependency history, pero añaden pasos de clone/update/publicación. Úsalos cuando importe la identidad independiente del repositorio; package manager o vendoring puede ser más simple cuando no importe.
