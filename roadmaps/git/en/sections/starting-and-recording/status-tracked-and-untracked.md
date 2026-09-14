# Status, Tracked, and Untracked Files

`git status` explains how the working tree and index differ from `HEAD`, and which files are not tracked at all. A tracked file can be unmodified, modified, staged, or simultaneously staged with newer unstaged edits.

```bash
git status
git status --short
```

Run status before destructive or history-changing operations. The short format is convenient for scripts and quick checks, but the full output often tells you exactly which restore, add, or conflict command is appropriate.
