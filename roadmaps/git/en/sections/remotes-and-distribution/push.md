# Push Refs Safely

Push sends objects the remote lacks and requests updates to remote refs. A normal push is rejected when it would discard remote history under the configured rules, which protects work added since your last known state.

```bash
git push -u origin feature/login
git push origin main
git push --force-with-lease
```

If rewriting a branch is intentional, prefer `--force-with-lease` over blind `--force`: the lease verifies that the remote ref still matches the state you expected. Protected server branches may reject rewriting regardless of local options.
