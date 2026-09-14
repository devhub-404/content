# Gestionando Dependencias

Go modules usan semantic versions y un module graph para resolver dependencies. `go get` cambia requirements, `go mod tidy` añade lo necesario y elimina lo no usado, y `go list` inspecciona el grafo.

```go
// Typical workflow:
// go get example.com/lib@v1.2.3
// go mod tidy
// go list -m all
```

Revisa upgrades como cambios de source, especialmente majors y dependencias transitivas. La checksum database y los proxies ayudan a la integridad, pero la seguridad también exige saber qué código y versiones entran en la aplicación.
