# Restore Working Tree or Index Content

`git restore` copies file content from a chosen source into the working tree and/or index; it does not move the branch tip. With no source specified it uses context-dependent defaults appropriate to restoring working or staged content.

```bash
git restore src/app.js
git restore --staged src/app.js
git restore --source=HEAD~1 src/app.js
```

Use restore when the question is “which version of this path should be in my working tree or staging area?” Check status and diff first because replacing unstaged working-tree content can discard edits that were never committed.
