# Regras de Ignore e Excludes

Regras de ignore afetam arquivos untracked que Git normalmente não deve oferecer para stage. `.gitignore` é política versionada do projeto; excludes locais e globais podem guardar padrões específicos da máquina ou usuário.

```bash
# .gitignore
node_modules/
*.log
.env.local
!important.log
```

Ignorar não deixa de rastrear arquivo já presente no histórico. Remova-o do index deliberadamente se o projeto deve parar de rastrear e não trate ignore como mecanismo de segurança para secrets já commitados.
