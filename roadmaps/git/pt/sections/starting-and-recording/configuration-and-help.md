# Configuração e Ajuda

A configuração Git pode existir em nível de sistema, usuário, repositório e, em setups modernos, worktree. Identidade afeta novos commits; aliases, editor, merge behavior, signing e defaults também podem ser configurados.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
git config --list --show-origin
git help commit
```

Use `--show-origin` quando um valor surpreender porque vários arquivos podem contribuir. Prefira configuração documentada a aliases de shell que escondem comportamento importante, especialmente em equipes.
