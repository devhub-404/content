# Blame, Grep, and History Search

Git can search both current content and historical changes. `git grep` searches tracked content, `git blame` annotates lines with the commits that last changed them, and pickaxe log options find commits that added or removed matching text or changed lines matching a pattern.

```bash
git grep "TODO"
git blame src/app.js
git log -S "oldFunction"
git log -G "pattern" -- '*.js'
```

Use blame as a navigation tool to context, not as a verdict about responsibility. Open the identified commit and surrounding history because line ownership can move through refactors, formatting, merges, and mechanical changes.
