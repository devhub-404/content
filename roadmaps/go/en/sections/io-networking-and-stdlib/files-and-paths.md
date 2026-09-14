# Files and Paths

The `os` package exposes files, process environment, and operating-system functionality, while `path/filepath` manipulates filesystem paths using platform-native separators. `path` is for slash-separated paths such as URL-style paths, not general local filesystem paths.

```go
data, err := os.ReadFile("config.json")
if err != nil {
    return err
}

path := filepath.Join("data", "report.txt")
fmt.Println(path, len(data))
```

Convenience functions like `os.ReadFile` are excellent for bounded files, while streaming through `os.File` is better for large data. Check errors from opens, reads, writes, syncs, and closes when durability matters. Filesystem operations can race with external changes.
