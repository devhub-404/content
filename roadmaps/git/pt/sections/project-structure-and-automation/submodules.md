# Submodules e Repositórios Aninhados

Submodule registra um commit específico de outro repositório em um path do superproject. O parent rastreia essa referência/configuração, não todo working state do repositório aninhado como arquivos comuns.

```bash
git submodule add <repository-url> libs/example
git submodule update --init --recursive
git clone --recurse-submodules <repository-url>
```

Submodules deixam dependency history explícito, mas adicionam passos de clone/update/publicação. Use quando identidade independente do repositório importa; package manager ou vendoring pode ser mais simples quando não importa.
