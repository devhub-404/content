# Snapshots y Objetos Git

Un commit no almacena un patch como modelo principal; referencia un tree snapshot y registra metadata como parents, author, committer y message. Los trees describen directorios, los blobs guardan contenido de archivos, los commits conectan snapshots y los annotated tags apuntan a otros objetos.

```bash
git cat-file -t HEAD
git cat-file -p HEAD
```

Los objetos se direccionan mediante object IDs derivados del contenido. Los plumbing commands rara vez son necesarios en el trabajo diario, pero entender los objetos vuelve mucho menos misteriosos branching, deduplicación, recovery y reescritura de historial.
