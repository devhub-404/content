---
locale: pt
status: published
title: "C++"
slug: cpp
description: "Uma referência rápida orientada a tarefas para sintaxe, APIs e workflows cotidianos de C++."
tags:
  - cpp
  - cheatsheet
  - quick-reference
references:
  - label: "cppreference: C++ language"
    url: https://en.cppreference.com/w/cpp/language
  - label: "cppreference: C++ standard library"
    url: https://en.cppreference.com/w/cpp/standard_library
  - label: "cppreference: C++23"
    url: https://en.cppreference.com/w/cpp/23
---

# C++

Referência rápida orientada a tarefas. Pesquise na página e copie o menor exemplo que corresponde ao que você precisa.

## Linguagem e Modelo de Build

**Translation Units, Linking e ODR**

```cpp
// math.hpp
#pragma once
int add(int a, int b);

// math.cpp
#include "math.hpp"
int add(int a, int b) { return a + b; }

// main.cpp
#include "math.hpp"
int main() { return add(2, 3) == 5 ? 0 : 1; }
```

**Headers, Modules e Includes**

```cpp
// geometry.cppm
export module geometry;

export struct point {
    double x;
    double y;
};

export double length(point p);
```

**Undefined Behavior e Abstract Machine**

```cpp
#include <limits>

int safe_increment(int x) {
    if (x == std::numeric_limits<int>::max()) {
        return x;
    }
    return x + 1;
}
```

## Valores, Tipos e Inicialização

**Tipos Fundamentais**

```cpp
#include <cstdint>
#include <limits>

std::int32_t temperature = -12;
double ratio = 0.75;
bool ready = true;
char separator = ':';
```

**Formas de Inicialização**

```cpp
int a = 10;
int b(20);
int c{30};

std::vector<int> values{1, 2, 3};
```

**`auto`, `decltype` e Dedução de Tipo**

```cpp
const int count = 42;
auto a = count;          // int
auto &b = count;         // const int&
decltype(count) c = 7;   // const int
```

**`const`, `constexpr` e Avaliação Constante**

```cpp
constexpr int square(int x) {
    return x * x;
}

constexpr int area = square(6);
const int runtime_value = read_value();
```

**Referências e Ponteiros**

```cpp
int value = 42;

int &ref = value;
int *ptr = &value;

ref = 50;
*ptr = 60;
```

**Categorias de Valor e Introdução a Move Semantics**

```cpp
std::string make_name() {
    std::string result = "Mina";
    return result;
}

std::string name = make_name();
std::string other = std::move(name);
```

## Fluxo de Controle e Funções

**Condicionais, Loops e Range-for**

```cpp
for (const auto &item : items) {
    if (!item.active) {
        continue;
    }
    process(item);
}
```

**Overloading de Funções e Argumentos Default**

```cpp
void log(int value);
void log(double value);
void log(std::string_view value);

void connect(std::string_view host, int port = 443);
```

**Lambdas e Captures**

```cpp
int factor = 3;

auto multiply = [factor](int value) {
    return value * factor;
};

std::ranges::transform(values, out.begin(), multiply);
```

**Templates de Função**

```cpp
template <typename T>
T max_value(T a, T b) {
    return b < a ? a : b;
}

auto best = max_value(10, 20);
```

**Variadic Templates e Fold Expressions**

```cpp
template <typename... Ts>
auto sum(Ts... values) {
    return (values + ...);
}

auto total = sum(1, 2, 3, 4);
```

## Classes e RAII

**Fundamentos de Classes e Encapsulamento**

```cpp
class account {
public:
    explicit account(std::string owner)
        : owner_(std::move(owner)) {}

    double balance() const {
        return balance_;
    }

private:
    std::string owner_;
    double balance_ = 0.0;
};
```

**Constructors e Inicialização de Membros**

```cpp
class point {
public:
    point(double x, double y)
        : x_(x), y_(y) {}

private:
    double x_;
    double y_;
};
```

**RAII e Destructors**

```cpp
class file {
public:
    explicit file(const char *path)
        : handle_(std::fopen(path, "r")) {}

    ~file() {
        if (handle_) std::fclose(handle_);
    }

private:
    std::FILE *handle_;
};
```

**Copy, Move e Special Member Functions**

```cpp
class buffer {
public:
    buffer(const buffer &) = delete;
    buffer &operator=(const buffer &) = delete;

    buffer(buffer &&) noexcept = default;
    buffer &operator=(buffer &&) noexcept = default;
};
```

**Operator Overloading**

```cpp
struct distance {
    double meters;
};

distance operator+(distance a, distance b) {
    return {a.meters + b.meters};
}
```

## Herança e Polimorfismo

**Herança e Funções Virtuais**

```cpp
class shape {
public:
    virtual ~shape() = default;
    virtual double area() const = 0;
};

class circle : public shape {
public:
    explicit circle(double r) : r_(r) {}
    double area() const override { return 3.14159 * r_ * r_; }

private:
    double r_;
};
```

**Object Slicing e Ownership Polimórfico**

```cpp
std::unique_ptr<shape> make_shape() {
    return std::make_unique<circle>(2.0);
}
```

**RTTI e `dynamic_cast`**

```cpp
shape &s = get_shape();

if (auto *c = dynamic_cast<circle *>(&s)) {
    std::cout << c->area() << '
';
}
```

## Ownership e Resource Management

**`std::unique_ptr`**

```cpp
auto user = std::make_unique<user_record>();
user->name = "Mina";

auto transferred = std::move(user);
```

**`std::shared_ptr` e `std::weak_ptr`**

```cpp
auto resource = std::make_shared<resource_type>();
std::weak_ptr<resource_type> observer = resource;

if (auto locked = observer.lock()) {
    use(*locked);
}
```

**Move Semantics e Perfect Forwarding**

```cpp
template <typename T, typename... Args>
std::unique_ptr<T> make_object(Args&&... args) {
    return std::make_unique<T>(
        std::forward<Args>(args)...
    );
}
```

**`std::span`, `std::string_view` e Views Borrowed**

```cpp
void print_values(std::span<const int> values) {
    for (int value : values) {
        std::cout << value << '
';
    }
}

void log(std::string_view message);
```

## Containers da Standard Library

**`vector`, `array` e `deque`**

```cpp
std::vector<int> values{1, 2, 3};
values.push_back(4);

std::array<int, 3> fixed{1, 2, 3};

std::deque<int> queue;
queue.push_front(1);
queue.push_back(2);
```

**Containers Associativos e Unordered**

```cpp
std::map<std::string, int> ordered;
ordered["alice"] = 10;

std::unordered_map<std::string, int> fast;
fast["bob"] = 20;

std::set<int> unique{1, 2, 3};
```

**Adaptadores `stack`, `queue` e `priority_queue`**

```cpp
std::queue<task> pending;
pending.push(task{});

std::priority_queue<int> priorities;
priorities.push(10);
priorities.push(5);
```

**Invalidation de Iterators e References**

```cpp
std::vector<int> values{1, 2, 3};
auto it = values.begin();

values.push_back(4);
// 'it' may now be invalid if reallocation occurred.
```

## Algoritmos, Ranges e Iterators

**Modelo de Iterators**

```cpp
auto first = values.begin();
auto last = values.end();

for (; first != last; ++first) {
    process(*first);
}
```

**Algoritmos Padrão**

```cpp
std::sort(values.begin(), values.end());

auto it = std::find(values.begin(), values.end(), target);

std::transform(
    values.begin(),
    values.end(),
    output.begin(),
    [](int x) { return x * 2; }
);
```

**Ranges e Views**

```cpp
auto even_squares =
    values
    | std::views::filter([](int x) { return x % 2 == 0; })
    | std::views::transform([](int x) { return x * x; });

for (int value : even_squares) {
    std::cout << value << '
';
}
```

**Comparators e Projections**

```cpp
std::ranges::sort(users, {}, &user::name);

auto found = std::ranges::find(
    users,
    "Mina",
    &user::name
);
```

## Templates e Concepts

**Class Templates**

```cpp
template <typename T>
class box {
public:
    explicit box(T value)
        : value_(std::move(value)) {}

    const T &get() const { return value_; }

private:
    T value_;
};
```

**Concepts e `requires`**

```cpp
#include <concepts>

template <typename T>
concept numeric = std::integral<T> || std::floating_point<T>;

template <numeric T>
T twice(T value) {
    return value + value;
}
```

**Specialization e Seleção de Overloads**

```cpp
template <typename T>
void print(const T &value);

template <>
void print<bool>(const bool &value);

void print(const char *value);
```

**Type Traits e Metaprogramação**

```cpp
#include <type_traits>

template <typename T>
constexpr bool is_small_integer =
    std::is_integral_v<T> && sizeof(T) <= 4;

static_assert(is_small_integer<int>);
```

## Erros e Sum Types

**Exceptions e Stack Unwinding**

```cpp
try {
    auto result = parse(input);
    use(result);
} catch (const parse_error &error) {
    std::cerr << error.what() << '
';
}
```

**`noexcept` e Exception Safety**

```cpp
class buffer {
public:
    buffer(buffer &&) noexcept = default;
    buffer &operator=(buffer &&) noexcept = default;
};
```

**`optional`, `variant` e `any`**

```cpp
std::optional<user> find_user(id value);

using result = std::variant<success, error>;

std::any metadata = std::string{"tag"};
```

**`std::expected` e Valores de Erro**

```cpp
std::expected<config, parse_error>
parse_config(std::string_view input) {
    // ...
}
```

## Concorrência

**Threads, `jthread` e Stop Tokens**

```cpp
std::jthread worker([](std::stop_token stop) {
    while (!stop.stop_requested()) {
        do_one_unit();
    }
});
```

**Mutexes, Locks e Condition Variables**

```cpp
std::mutex mutex;
std::condition_variable cv;
bool ready = false;

{
    std::lock_guard lock(mutex);
    ready = true;
}
cv.notify_one();
```

**Atômicos e Memory Ordering**

```cpp
std::atomic<unsigned> counter{0};

counter.fetch_add(
    1,
    std::memory_order_relaxed
);
```

**Futures e `std::async`**

```cpp
auto future = std::async(
    std::launch::async,
    [] { return expensive_work(); }
);

auto result = future.get();
```

## Recursos da Biblioteca

**Strings, String Views e Formatting**

```cpp
std::string name = "Mina";
std::string_view view = name;

std::string message =
    std::format("Hello, {}!", view);
```

**Filesystem**

```cpp
namespace fs = std::filesystem;

for (const auto &entry :
     fs::directory_iterator(".")) {
    std::cout << entry.path() << '
';
}
```

**Tempo com `<chrono>`**

```cpp
using namespace std::chrono;

auto start = steady_clock::now();
do_work();
auto elapsed = steady_clock::now() - start;

std::cout
    << duration_cast<milliseconds>(elapsed).count()
    << " ms
";
```

**Random Numbers**

```cpp
std::random_device rd;
std::mt19937 engine(rd());

std::uniform_int_distribution<int> die(1, 6);

int roll = die(engine);
```

## Tooling, Qualidade e Prática Moderna

**Warnings, Sanitizers e Static Analysis**

```cpp
// Example build:
// c++ -std=c++23 -Wall -Wextra -Wconversion //     -fsanitize=address,undefined main.cpp
```

**Depuração de C++ Nativo**

```cpp
std::vector<int> values{1, 2, 3};
std::cout << values.at(10) << '
';
```

**Design de API e Value Semantics**

```cpp
class user_id {
public:
    explicit user_id(std::uint64_t value)
        : value_(value) {}

    std::uint64_t value() const noexcept {
        return value_;
    }

private:
    std::uint64_t value_;
};
```

**Performance e Zero-cost Abstractions**

```cpp
template <std::ranges::input_range R>
auto total(const R &range) {
    using value_type =
        std::ranges::range_value_t<R>;

    value_type sum{};
    for (const auto &value : range) {
        sum += value;
    }
    return sum;
}
```
