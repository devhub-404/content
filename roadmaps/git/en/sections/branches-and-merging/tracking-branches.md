# Tracking and Upstream Branches

A local branch can record an upstream branch used as the default comparison/integration target for commands such as status, pull, and push. Remote-tracking refs such as `origin/main` are local records of what a remote ref looked like after the last fetch.

```bash
git branch -vv
git push -u origin feature/login
git rev-parse --abbrev-ref --symbolic-full-name @{upstream}
```

Do not confuse `origin/main` with a live branch on the server. Fetch updates that local remote-tracking ref; your local `main` remains separate until you merge, rebase, reset, or otherwise move it.
