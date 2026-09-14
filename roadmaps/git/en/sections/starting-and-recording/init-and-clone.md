# Initialize and Clone Repositories

`git init` creates repository metadata for an existing directory; `git clone` creates a new local repository from another repository and normally checks out its default branch. A clone receives repository history and remote configuration, not merely a folder copy.

```bash
git init
git clone <repository-url>
git clone --depth 1 <repository-url>
```

Shallow clones intentionally limit available history and can affect history-based tools. Use them when the tradeoff is appropriate, but deepen or fetch full history before assuming every ancestor is locally available.
