# Versiones del Lenguaje y Compatibilidad

Los modules declaran una versión Go que controla la semántica esperada del lenguaje. Los toolchains evolucionan por separado y versiones nuevas pueden compilar modules dirigidos a versiones anteriores compatibles.

```go
// go.mod
module example.com/project

go 1.27
```

Al usar una feature nueva, comprueba si pertenece al lenguaje, standard library o toolchain y qué minimum version exige. Mantén honesta la versión declarada para que consumers y tooling reciban la señal correcta.
