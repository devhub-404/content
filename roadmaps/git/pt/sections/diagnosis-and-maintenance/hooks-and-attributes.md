# Hooks e Attributes por Path

Hooks executam programas locais ou server-side em torno de operações Git; attributes atribuem comportamento por path como normalization, diff drivers, merge behavior e export settings. São mecanismos diferentes de automação.

```bash
# .gitattributes
*.sh text eol=lf
*.png binary

# .git/hooks/pre-commit (or configured hooks path)
# run project checks before accepting a commit
```

Client hooks não são distribuídos automaticamente só por clone, então não dependa deles como única enforcement de policy. Versione scripts/configuração e conecte por setup documentado ou checks no servidor.
