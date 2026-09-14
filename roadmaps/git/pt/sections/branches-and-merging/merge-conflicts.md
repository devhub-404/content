# Resolver Conflitos de Merge

Conflito significa que Git não consegue escolher automaticamente um resultado combinado para certos paths. Durante merge, o index pode guardar múltiplos stages do path enquanto working file contém conflict markers ou conteúdo do merge tool.

```bash
git status
# edit conflicted files
git add <resolved-files>
git merge --continue
# or: git merge --abort
```

Edite o arquivo para o resultado final desejado, faça stage e continue. Use status como fonte de verdade e abort quando quiser voltar ao estado pré-merge em vez de improvisar resets no meio do conflito.
