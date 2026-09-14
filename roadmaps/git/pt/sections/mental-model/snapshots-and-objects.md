# Snapshots e Objetos Git

Um commit não armazena um patch como modelo primário; ele referencia um tree snapshot e registra metadata como parents, author, committer e message. Trees descrevem diretórios, blobs guardam conteúdo de arquivos, commits conectam snapshots e annotated tags apontam para outros objetos.

```bash
git cat-file -t HEAD
git cat-file -p HEAD
```

Objetos são endereçados por object IDs derivados do conteúdo. Plumbing commands raramente são necessários no dia a dia, mas entender objetos torna branching, deduplicação, recovery e reescrita de histórico muito menos misteriosos.
