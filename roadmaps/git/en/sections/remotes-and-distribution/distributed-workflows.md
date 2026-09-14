# Forks, Upstreams, and Distributed Workflows

Because every clone is a repository with history, collaboration does not require one physical topology. A contributor can push to a fork, maintainers can fetch contributor refs, and projects can use central, integration-manager, or multi-remote workflows while still exchanging the same Git objects.

```bash
git remote add upstream <canonical-url>
git fetch upstream
git rebase upstream/main
```

Separate Git's distributed mechanics from hosting-platform review features. Pull requests and merge requests coordinate discussion and server policy; fetch, push, branches, and commits remain the underlying Git data model.
