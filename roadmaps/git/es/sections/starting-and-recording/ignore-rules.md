# Reglas de Ignore y Excludes

Las reglas de ignore afectan archivos untracked que Git normalmente no debe ofrecer para stage. `.gitignore` es política versionada del proyecto; excludes locales y globales pueden guardar patrones específicos de la máquina o usuario.

```bash
# .gitignore
node_modules/
*.log
.env.local
!important.log
```

Ignorar no deja de rastrear un archivo ya presente en el historial. Sácalo del index deliberadamente si el proyecto debe dejar de rastrearlo y no trates ignore como mecanismo de seguridad para secrets ya committeados.
