---
locale: pt
status: published
title: "PHP"
slug: php
description: "Uma referência rápida orientada a tarefas para sintaxe, APIs e workflows cotidianos de PHP."
tags:
  - php
  - cheatsheet
  - quick-reference
references:
  - label: "PHP Manual"
    url: https://www.php.net/manual/en/
  - label: "PHP Language Reference"
    url: https://www.php.net/manual/en/langref.php
  - label: "PHP Security"
    url: https://www.php.net/manual/en/security.php
---

# PHP

Referência rápida orientada a tarefas. Pesquise na página e copie o menor exemplo que corresponde ao que você precisa.

## Linguagem, Runtime e Requests

**Arquivos PHP, Tags e Output**

```php
<?php

declare(strict_types=1);

$message = 'hello';
echo $message, PHP_EOL;
```

**Lifecycle de Request e Superglobals**

```php
<?php
$method = $_SERVER['REQUEST_METHOD'] ?? 'GET';
$query = $_GET['q'] ?? null;

if ($query !== null) {
    echo htmlspecialchars($query, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
}
```

**Programas CLI**

```php
<?php
$args = $argv;
$script = array_shift($args);

foreach ($args as $arg) {
    echo $arg, PHP_EOL;
}
```

## Valores, Tipos e Strings

**Tipos Escalares e `null`**

```php
$count = 42;
$ratio = 0.75;
$name = 'Mina';
$ready = true;
$missing = null;
```

**Strict Types e Declarações de Tipo**

```php
<?php
declare(strict_types=1);

function add(int $a, int $b): int {
    return $a + $b;
}
```

**Union, Intersection e Nullable Types**

```php
function normalize(string|Stringable $value): string {
    return (string) $value;
}

function save(?User $user): void {
    // ...
}
```

**Strings, Interpolation, Heredoc e Nowdoc**

```php
$name = 'Mina';
$message = "Hello, {$name}!";

$sql = <<<SQL
SELECT id, name
FROM users
WHERE active = 1
SQL;
```

**Type Juggling, Comparações e `match`**

```php
$input = '0';

if ($input === 0) {
    echo 'integer zero';
}

$label = match ($status) {
    Status::Ready => 'ready',
    Status::Failed => 'failed',
};
```

## Arrays, Collections e Iteration

**Arrays PHP**

```php
$list = ['a', 'b', 'c'];
$map = ['name' => 'Mina', 'active' => true];

$list[] = 'd';
$map['role'] = 'admin';
```

**Funções de Array e Transformações**

```php
$activeNames = array_map(
    fn (User $user) => $user->name,
    array_filter($users, fn (User $user) => $user->active),
);
```

**`foreach`, `iterable` e Iterators**

```php
foreach ($users as $id => $user) {
    echo $id, ': ', $user->name, PHP_EOL;
}

function names(iterable $users): iterable {
    foreach ($users as $user) {
        yield $user->name;
    }
}
```

**Generators e `yield`**

```php
function lines(string $path): Generator {
    $file = fopen($path, 'rb');
    try {
        while (($line = fgets($file)) !== false) {
            yield rtrim($line, "
");
        }
    } finally {
        fclose($file);
    }
}
```

## Functions, Closures e Expressions Modernas

**Functions e Parâmetros**

```php
function connect(
    string $host,
    int $port = 443,
    bool $secure = true,
): void {
    // ...
}

connect(host: 'example.com', secure: false);
```

**Closures, Arrow Functions e Capture**

```php
$factor = 3;

$multiply = fn (int $value): int => $value * $factor;

$counter = 0;
$next = function () use (&$counter): int {
    return ++$counter;
};
```

**First-class Callables e Pipe Operator**

```php
$slug = ' PHP 8.5 Released '
    |> trim(...)
    |> (fn (string $s) => str_replace(' ', '-', $s))
    |> strtolower(...);
```

**References e Copy-on-write**

```php
$a = [1, 2, 3];
$b = $a;
$b[] = 4;

$c =& $a;
$c[] = 5;
```

## Objetos e Modelos de Domínio

**Classes, Properties e Constructors**

```php
final class Account
{
    public function __construct(
        public readonly string $owner,
        private int $balance = 0,
    ) {}

    public function balance(): int { return $this->balance; }
}
```

**Herança, Abstract, Final e Interfaces**

```php
interface Clock
{
    public function now(): DateTimeImmutable;
}

abstract class BaseService
{
    abstract public function run(): void;
}

final class Service extends BaseService implements Clock
{
    // ...
}
```

**Traits**

```php
trait LogsActions
{
    private function log(string $message): void
    {
        error_log($message);
    }
}

final class Service
{
    use LogsActions;
}
```

**Enums**

```php
enum Status: string
{
    case Pending = 'pending';
    case Ready = 'ready';
    case Failed = 'failed';
}
```

**Attributes e Reflection**

```php
#[Attribute(Attribute::TARGET_CLASS)]
final class Route
{
    public function __construct(public string $path) {}
}

#[Route('/users')]
final class UserController {}
```

**Properties Modernas e Design Readonly**

```php
final class User
{
    public string $name {
        set => trim($value);
    }

    public function __construct(string $name)
    {
        $this->name = $name;
    }
}
```

## Erros, Recursos e Execução

**Exceptions, `Throwable` e `finally`**

```php
try {
    process($input);
} catch (DomainException $e) {
    report($e);
} finally {
    cleanup();
}
```

**Error Reporting e Handlers**

```php
error_reporting(E_ALL);

set_exception_handler(function (Throwable $e): void {
    error_log((string) $e);
    http_response_code(500);
});
```

**Files, Streams e Resource Handles**

```php
$handle = fopen($path, 'rb');
if ($handle === false) {
    throw new RuntimeException('cannot open file');
}

try {
    $data = stream_get_contents($handle);
} finally {
    fclose($handle);
}
```

**Fibers e Concorrência Cooperativa**

```php
$fiber = new Fiber(function (): void {
    $value = Fiber::suspend('paused');
    echo $value;
});

$state = $fiber->start();
$fiber->resume('resumed');
```

## Input Web, Output e Segurança

**Forms, Query Strings e Validação**

```php
$email = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);

if ($email === false || $email === null) {
    http_response_code(422);
    exit;
}
```

**Output HTML e XSS**

```php
<?= htmlspecialchars(
    $user->displayName,
    ENT_QUOTES | ENT_SUBSTITUTE,
    'UTF-8'
) ?>
```

**Cookies, Sessions e CSRF**

```php
session_start();
$_SESSION['user_id'] = $userId;

setcookie('theme', 'dark', [
    'secure' => true,
    'httponly' => true,
    'samesite' => 'Lax',
]);
```

**Senhas e APIs Criptográficas**

```php
$hash = password_hash($password, PASSWORD_DEFAULT);

if (!password_verify($candidate, $hash)) {
    throw new AuthenticationException();
}
```

**File Uploads**

```php
if (!isset($_FILES['avatar']) || $_FILES['avatar']['error'] !== UPLOAD_ERR_OK) {
    throw new RuntimeException('upload failed');
}

$tmp = $_FILES['avatar']['tmp_name'];
move_uploaded_file($tmp, $destination);
```

## Databases e Dados Externos

**PDO e Prepared Statements**

```php
$pdo = new PDO($dsn, $user, $password, [
    PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION,
]);

$stmt = $pdo->prepare('SELECT id, name FROM users WHERE email = :email');
$stmt->execute(['email' => $email]);
```

**Transactions**

```php
$pdo->beginTransaction();
try {
    debit($pdo, $from, $amount);
    credit($pdo, $to, $amount);
    $pdo->commit();
} catch (Throwable $e) {
    $pdo->rollBack();
    throw $e;
}
```

**JSON e Payloads de API**

```php
$data = json_decode($json, true, flags: JSON_THROW_ON_ERROR);

$response = json_encode(
    ['id' => 42, 'name' => 'Mina'],
    JSON_THROW_ON_ERROR,
);
```

## Composer, Autoloading e Arquitetura

**Namespaces e Autoloading PSR-4**

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

**Dependencies Composer e Lock Files**

```json
{
  "require": {
    "php": "^8.5",
    "psr/log": "^3.0"
  }
}
```

**Dependency Injection e Service Boundaries**

```php
final class ReportService
{
    public function __construct(
        private Clock $clock,
        private ReportRepository $reports,
    ) {}
}
```

## Testes, Análise e Produção

**Unit Testing e PHPUnit**

```php
final class CalculatorTest extends TestCase
{
    public function testAdd(): void
    {
        self::assertSame(5, (new Calculator())->add(2, 3));
    }
}
```

**Static Analysis e Coding Standards**

```php
<?php
/** @return list<User> */
function activeUsers(): array {
    // ...
}
```

**OPcache, Memória e Performance**

```php
<?php
// Production typically enables OPcache in php.ini.
// Measure application hot paths before manual micro-optimization.
```

**Configuração, Secrets e Environments**

```php
$dsn = getenv('DATABASE_DSN');
if ($dsn === false) {
    throw new RuntimeException('DATABASE_DSN is required');
}
```
