# Submodules and Nested Repositories

A submodule records a specific commit of another repository at a path in the superproject. The parent repository tracks that commit reference and configuration, not the nested repository's full working state as ordinary files.

```bash
git submodule add <repository-url> libs/example
git submodule update --init --recursive
git clone --recurse-submodules <repository-url>
```

Submodules make dependency history explicit but add coordination steps for cloning, updating, and publishing pointer changes. Use them when independent repository identity matters; package managers or vendoring may be simpler when it does not.
