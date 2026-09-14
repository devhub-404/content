# Stage Changes with `git add`

`git add` copies selected working-tree content into the index, preparing the exact snapshot that the next commit will record. Running add again after more edits updates the staged version; staging is not a permanent relationship with the file.

```bash
git add src/app.js
git add -p
git add -u
```

Interactive patch mode lets one file contribute only selected hunks to a commit. This is valuable for producing focused commits when the working tree contains several logically separate changes.
