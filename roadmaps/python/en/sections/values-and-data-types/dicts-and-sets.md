# Dictionaries and Sets

A `dict` maps hashable keys to values and preserves insertion order as a language guarantee. A `set` stores unique hashable values and supports mathematical set operations. Both use hashing and equality, so keys/elements must have stable hash/equality behavior while stored.

```python
counts = {"ready": 2, "failed": 1}
counts["ready"] += 1

seen = {"python", "typing"}
seen.add("asyncio")
```

Use dictionaries for named lookup and sets for uniqueness/membership rather than repeatedly scanning lists. Prefer `dict.get`, `setdefault`, `collections.defaultdict`, or `Counter` when those APIs directly express the operation.
