# Inicializar y Clonar Repositorios

`git init` crea metadata de repositorio en un directorio existente; `git clone` crea un repositorio local desde otro y normalmente hace checkout de la branch default. Un clone recibe historial y remote configuration, no solo una copia de carpeta.

```bash
git init
git clone <repository-url>
git clone --depth 1 <repository-url>
```

Los shallow clones limitan el historial intencionalmente y afectan herramientas basadas en ancestry. Úsalos cuando el tradeoff tenga sentido, pero profundiza el historial antes de asumir que todo ancestor está disponible.
