# Read History with `log` and `show`

`git log` walks reachable commit history and can filter, format, graph, and limit that traversal. `git show` displays one object, commonly a commit with its metadata and patch.

```bash
git log --oneline --graph --decorate --all
git show --stat HEAD
git log -- path/to/file
```

History is a graph, so filters such as paths, authors, dates, ancestry, and grep can change which commits appear. Build a log command around the question you are answering instead of memorizing one giant format for every investigation.
