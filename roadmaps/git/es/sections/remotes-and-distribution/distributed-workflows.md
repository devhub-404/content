# Forks, Upstreams y Workflows Distribuidos

Como cada clone es un repositorio con historial, la colaboración no exige una única topología física. Un contributor puede hacer push a un fork, maintainers pueden fetch refs y proyectos pueden usar workflows centrales o multi-remote intercambiando los mismos objetos Git.

```bash
git remote add upstream <canonical-url>
git fetch upstream
git rebase upstream/main
```

Separa la mecánica distribuida de Git de las features de review de la plataforma. Pull/merge requests coordinan discusión y policy del servidor; fetch, push, branches y commits siguen siendo el modelo de datos subyacente.
