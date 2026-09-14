# Remote Configuration

A remote is a named set of URLs and ref-mapping configuration used for fetching and pushing. `origin` is only a conventional default name created by clone; repositories can have several remotes for forks, mirrors, or separate publishing targets.

```bash
git remote -v
git remote add upstream <repository-url>
git remote set-url origin <new-url>
```

Name remotes by role when more than one exists, such as `origin` for your fork and `upstream` for the canonical project. Inspect the URLs before pushing when repositories have similar names or sensitive destinations.
