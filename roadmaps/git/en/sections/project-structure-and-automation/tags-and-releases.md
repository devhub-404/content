# Tags, Releases, and Signing

Tags give stable names to selected objects, commonly release commits. Annotated tags are full Git objects with metadata and a message and can be cryptographically signed; lightweight tags are simple refs.

```bash
git tag -a v1.0.0 -m "Release 1.0.0"
git push origin v1.0.0
git tag -v v1.0.0
```

Push tags deliberately because ordinary branch push behavior does not necessarily publish every local tag. Signing proves a relationship to a key identity only within the trust model your project actually verifies.
