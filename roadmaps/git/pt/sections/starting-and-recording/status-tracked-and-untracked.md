# Status, Arquivos Tracked e Untracked

`git status` explica como working tree e index diferem de `HEAD` e quais arquivos não são tracked. Um arquivo tracked pode estar unmodified, modified, staged ou ter simultaneamente uma versão staged e edits mais novos unstaged.

```bash
git status
git status --short
```

Rode status antes de operações destrutivas ou que mudam histórico. O formato curto é ótimo para checks rápidos, mas a saída completa frequentemente indica exatamente qual add, restore ou comando de conflito usar.
