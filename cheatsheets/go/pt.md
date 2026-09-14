---
locale: pt
status: published
title: "Go"
slug: go
description: "Uma referência rápida orientada a tarefas para sintaxe, APIs e workflows cotidianos de Go."
tags:
  - go
  - cheatsheet
  - quick-reference
references:
  - label: "The Go Programming Language Specification"
    url: https://go.dev/ref/spec
  - label: "A Tour of Go"
    url: https://go.dev/tour/
  - label: "Go Documentation"
    url: https://go.dev/doc/
---

# Go

Referência rápida orientada a tarefas. Pesquise na página e copie o menor exemplo que corresponde ao que você precisa.

## Linguagem e Toolchain

**Comando `go` e Workflow Diário**

```go
// Typical commands:
// go run .
// go test ./...
// go fmt ./...
// go vet ./...
// go build ./...
```

**Packages e Imports**

```go
package report

import (
    "fmt"
    "time"
)

func PrintNow() {
    fmt.Println(time.Now())
}
```

**Identifiers Exportados e Documentação**

```go
package geometry

// Point represents a location in 2D space.
type Point struct {
    X float64
    Y float64
}
```

## Variáveis, Tipos e Valores

**Variáveis e Zero Values**

```go
var count int
var ready bool
var name string

fmt.Println(count, ready, name)
// 0 false ""
```

**`var`, Declaração Curta e Constants**

```go
var host string = "example.com"
port := 443

const timeoutSeconds = 30
const Pi = 3.141592653589793
```

**Tipos Básicos e Conversões**

```go
var age int = 42
var ratio float64 = 0.75
var enabled bool = true
var text string = "Go"

converted := float64(age)
```

**Strings, Bytes e Runes**

```go
text := "Olá, 世界"

fmt.Println(len(text)) // bytes

for i, r := range text {
    fmt.Println(i, r)
}
```

**Tipos Definidos e Aliases**

```go
type UserID string
type HandlerFunc = func(Request) Response

var id UserID = "u-42"
```

## Fluxo de Controle e Funções

**`if`, `switch` e `for`**

```go
if value, err := read(); err != nil {
    return err
} else {
    fmt.Println(value)
}

for i := 0; i < 10; i++ {
    fmt.Println(i)
}
```

**`range` sobre Coleções e Iterators**

```go
for index, value := range values {
    fmt.Println(index, value)
}

for key, value := range lookup {
    fmt.Println(key, value)
}
```

**Funções e Múltiplos Retornos**

```go
func divide(a, b float64) (float64, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}
```

**Funções Variádicas**

```go
func sum(values ...int) int {
    total := 0
    for _, value := range values {
        total += value
    }
    return total
}

total := sum(1, 2, 3)
```

**Function Values e Closures**

```go
func makeCounter() func() int {
    count := 0

    return func() int {
        count++
        return count
    }
}
```

**`defer` e Cleanup**

```go
file, err := os.Open(path)
if err != nil {
    return err
}
defer file.Close()

// use file
```

## Arrays, Slices e Maps

**Arrays**

```go
var a [3]int
b := [3]int{10, 20, 30}

fmt.Println(a, b)
```

**Slices, Length, Capacity e `append`**

```go
values := make([]int, 0, 4)
values = append(values, 10, 20, 30)

fmt.Println(len(values), cap(values))
```

**Cópia e Aliasing de Slices**

```go
src := []int{1, 2, 3}
dst := make([]int, len(src))

copy(dst, src)
dst[0] = 99
```

**Maps**

```go
counts := map[string]int{
    "go": 2,
}

counts["rust"]++

value, ok := counts["missing"]
fmt.Println(value, ok)
```

**`make`, `new` e Alocação**

```go
values := make([]int, 10)
lookup := make(map[string]int)

ptr := new(int)
*ptr = 42
```

## Structs, Methods e Interfaces

**Structs e Embedding**

```go
type Address struct {
    City string
}

type User struct {
    Name string
    Address
}

u := User{
    Name: "Mina",
    Address: Address{City: "Lisbon"},
}
```

**Methods e Receivers**

```go
type Counter struct {
    value int
}

func (c *Counter) Inc() {
    c.value++
}

func (c Counter) Value() int {
    return c.value
}
```

**Interfaces e Satisfação Implícita**

```go
type Writer interface {
    Write([]byte) (int, error)
}

func save(w Writer, data []byte) error {
    _, err := w.Write(data)
    return err
}
```

**`any`, Type Assertions e Type Switches**

```go
func describe(value any) string {
    switch v := value.(type) {
    case string:
        return v
    case int:
        return strconv.Itoa(v)
    default:
        return "unknown"
    }
}
```

**Interfaces Nil e Valores Nil Tipados**

```go
var p *bytes.Buffer = nil
var w io.Writer = p

fmt.Println(w == nil) // false
```

## Erros e Controle Excepcional

**Errors como Valores**

```go
func load(path string) ([]byte, error) {
    data, err := os.ReadFile(path)
    if err != nil {
        return nil, fmt.Errorf("load %q: %w", path, err)
    }
    return data, nil
}
```

**`errors.Is`, `errors.As` e Wrapping**

```go
if errors.Is(err, os.ErrNotExist) {
    // handle missing file
}

var pathErr *fs.PathError
if errors.As(err, &pathErr) {
    fmt.Println(pathErr.Path)
}
```

**`panic` e `recover`**

```go
func mustPositive(value int) {
    if value <= 0 {
        panic("value must be positive")
    }
}
```

## Generics

**Type Parameters e Constraints**

```go
func Max[T cmp.Ordered](a, b T) T {
    if a > b {
        return a
    }
    return b
}
```

**Tipos Genéricos**

```go
type Stack[T any] struct {
    items []T
}

func (s *Stack[T]) Push(value T) {
    s.items = append(s.items, value)
}

func (s *Stack[T]) Pop() (T, bool) {
    var zero T
    if len(s.items) == 0 {
        return zero, false
    }
    last := len(s.items) - 1
    value := s.items[last]
    s.items = s.items[:last]
    return value, true
}
```

**Type Sets e Constraints de Underlying Type**

```go
type Integer interface {
    ~int | ~int32 | ~int64
}

func Double[T Integer](value T) T {
    return value * 2
}
```

## Goroutines, Channels e Sincronização

**Goroutines**

```go
go func() {
    result := doWork()
    results <- result
}()
```

**Channels**

```go
jobs := make(chan int)

go func() {
    for job := range jobs {
        process(job)
    }
}()

jobs <- 42
close(jobs)
```

**`select` e Multiplexação**

```go
select {
case value := <-results:
    use(value)
case <-time.After(time.Second):
    return errors.New("timeout")
}
```

**Mutexes, WaitGroups e Once**

```go
var mu sync.Mutex
var count int

mu.Lock()
count++
mu.Unlock()
```

**`context` para Cancellation e Deadlines**

```go
func load(ctx context.Context) error {
    req, err := http.NewRequestWithContext(
        ctx,
        http.MethodGet,
        endpoint,
        nil,
    )
    if err != nil {
        return err
    }

    _, err = http.DefaultClient.Do(req)
    return err
}
```

**Memory Model e Data Races**

```go
var value int
var ready atomic.Bool

go func() {
    value = 42
    ready.Store(true)
}()

if ready.Load() {
    fmt.Println(value)
}
```

## I/O, Networking e Standard Library

**`io.Reader` e `io.Writer`**

```go
func copyToFile(
    dst io.Writer,
    src io.Reader,
) error {
    _, err := io.Copy(dst, src)
    return err
}
```

**Arquivos e Paths**

```go
data, err := os.ReadFile("config.json")
if err != nil {
    return err
}

path := filepath.Join("data", "report.txt")
fmt.Println(path, len(data))
```

**JSON e Encoding**

```go
type User struct {
    ID   string `json:"id"`
    Name string `json:"name"`
}

var user User
if err := json.Unmarshal(data, &user); err != nil {
    return err
}
```

**Clientes e Servidores HTTP**

```go
mux := http.NewServeMux()

mux.HandleFunc("GET /health", func(
    w http.ResponseWriter,
    r *http.Request,
) {
    w.WriteHeader(http.StatusNoContent)
})

server := &http.Server{
    Addr:    ":8080",
    Handler: mux,
}
```

**Tempo, Timers e Tickers**

```go
deadline := time.Now().Add(5 * time.Second)

timer := time.NewTimer(time.Second)
defer timer.Stop()

select {
case <-timer.C:
    fmt.Println(deadline)
case <-ctx.Done():
    return ctx.Err()
}
```

## Testes e Qualidade

**Unit Tests e Table-driven Tests**

```go
func TestAdd(t *testing.T) {
    tests := []struct {
        name string
        a, b int
        want int
    }{
        {"positive", 2, 3, 5},
        {"zero", 0, 4, 4},
    }

    for _, tt := range tests {
        t.Run(tt.name, func(t *testing.T) {
            if got := Add(tt.a, tt.b); got != tt.want {
                t.Fatalf("got %d, want %d", got, tt.want)
            }
        })
    }
}
```

**Benchmarks e Profiling**

```go
func BenchmarkParse(b *testing.B) {
    input := []byte("example")

    for b.Loop() {
        Parse(input)
    }
}
```

**Fuzz Testing**

```go
func FuzzParse(f *testing.F) {
    f.Add("seed")

    f.Fuzz(func(t *testing.T, input string) {
        _ = Parse(input)
    })
}
```

**Race Detector e `go vet`**

```go
// Typical checks:
// go test -race ./...
// go vet ./...
```

## Modules e Dependências

**`go.mod` e Module Paths**

```go
module example.com/project

go 1.27

require example.com/dependency v1.4.0
```

**Gerenciando Dependências**

```go
// Typical workflow:
// go get example.com/lib@v1.2.3
// go mod tidy
// go list -m all
```

**Versionamento de Modules e Major Versions**

```go
// v1 import:
import "example.com/lib"

// v2+ import:
import "example.com/lib/v2"
```

**Go Workspaces**

```go
// go.work
go 1.27

use (
    ./service
    ./library
)
```

## Design de Produção e Performance

**Design de API e Interfaces Pequenas**

```go
type Clock interface {
    Now() time.Time
}

func NewService(clock Clock) *Service {
    return &Service{clock: clock}
}
```

**Alocação e Escape Analysis**

```go
func build() *int {
    value := 42
    return &value
}
```

**Garbage Collection e Lifetimes**

```go
type Cache struct {
    data map[string][]byte
}

func (c *Cache) Clear() {
    clear(c.data)
}
```
