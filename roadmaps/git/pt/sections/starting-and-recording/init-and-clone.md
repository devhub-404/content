# Inicializar e Clonar Repositórios

`git init` cria metadata de repositório em diretório existente; `git clone` cria repositório local a partir de outro e normalmente faz checkout da branch default. Um clone recebe histórico e remote configuration, não apenas uma cópia de pasta.

```bash
git init
git clone <repository-url>
git clone --depth 1 <repository-url>
```

Shallow clones limitam histórico intencionalmente e afetam ferramentas baseadas em ancestry. Use quando a troca fizer sentido, mas aprofunde o histórico antes de assumir que todo ancestor está disponível.
