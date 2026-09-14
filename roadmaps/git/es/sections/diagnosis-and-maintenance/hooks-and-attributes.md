# Hooks y Attributes por Path

Los hooks ejecutan programas locales o server-side alrededor de operaciones Git; los attributes asignan comportamiento por path como normalization, diff drivers, merge behavior y export settings. Son mecanismos distintos de automatización.

```bash
# .gitattributes
*.sh text eol=lf
*.png binary

# .git/hooks/pre-commit (or configured hooks path)
# run project checks before accepting a commit
```

Los client hooks no se distribuyen automáticamente solo por clone, así que no dependas de ellos como única enforcement de policy. Versiona scripts/configuración y conéctalos mediante setup documentado o checks del servidor.
