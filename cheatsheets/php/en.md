---
locale: en
status: published
title: "PHP"
slug: php
description: "A task-oriented quick reference for everyday PHP syntax, APIs, and workflows."
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

Task-oriented quick reference. Search the page and copy the smallest example that matches what you need.

## Language, Runtime & Requests

**PHP Files, Tags, and Output**

```php
<?php

declare(strict_types=1);

$message = 'hello';
echo $message, PHP_EOL;
```

**Request Lifecycle and Superglobals**

```php
<?php
$method = $_SERVER['REQUEST_METHOD'] ?? 'GET';
$query = $_GET['q'] ?? null;

if ($query !== null) {
    echo htmlspecialchars($query, ENT_QUOTES | ENT_SUBSTITUTE, 'UTF-8');
}
```

**CLI Programs**

```php
<?php
$args = $argv;
$script = array_shift($args);

foreach ($args as $arg) {
    echo $arg, PHP_EOL;
}
```

## Values, Types & Strings

**Scalar Types and `null`**

```php
$count = 42;
$ratio = 0.75;
$name = 'Mina';
$ready = true;
$missing = null;
```

**Strict Types and Type Declarations**

```php
<?php
declare(strict_types=1);

function add(int $a, int $b): int {
    return $a + $b;
}
```

**Union, Intersection, and Nullable Types**

```php
function normalize(string|Stringable $value): string {
    return (string) $value;
}

function save(?User $user): void {
    // ...
}
```

**Strings, Interpolation, Heredoc, and Nowdoc**

```php
$name = 'Mina';
$message = "Hello, {$name}!";

$sql = <<<SQL
SELECT id, name
FROM users
WHERE active = 1
SQL;
```

**Type Juggling, Comparisons, and `match`**

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

## Arrays, Collections & Iteration

**PHP Arrays**

```php
$list = ['a', 'b', 'c'];
$map = ['name' => 'Mina', 'active' => true];

$list[] = 'd';
$map['role'] = 'admin';
```

**Array Functions and Transformations**

```php
$activeNames = array_map(
    fn (User $user) => $user->name,
    array_filter($users, fn (User $user) => $user->active),
);
```

**`foreach`, `iterable`, and Iterators**

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

**Generators and `yield`**

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

## Functions, Closures & Modern Expressions

**Functions and Parameters**

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

**Closures, Arrow Functions, and Capture**

```php
$factor = 3;

$multiply = fn (int $value): int => $value * $factor;

$counter = 0;
$next = function () use (&$counter): int {
    return ++$counter;
};
```

**First-class Callables and the Pipe Operator**

```php
$slug = ' PHP 8.5 Released '
    |> trim(...)
    |> (fn (string $s) => str_replace(' ', '-', $s))
    |> strtolower(...);
```

**References and Copy-on-write Semantics**

```php
$a = [1, 2, 3];
$b = $a;
$b[] = 4;

$c =& $a;
$c[] = 5;
```

## Objects & Domain Models

**Classes, Properties, and Constructors**

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

**Inheritance, Abstract, Final, and Interfaces**

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

**Attributes and Reflection**

```php
#[Attribute(Attribute::TARGET_CLASS)]
final class Route
{
    public function __construct(public string $path) {}
}

#[Route('/users')]
final class UserController {}
```

**Modern Properties and Readonly Design**

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

## Errors, Resources & Execution

**Exceptions, `Throwable`, and `finally`**

```php
try {
    process($input);
} catch (DomainException $e) {
    report($e);
} finally {
    cleanup();
}
```

**Error Reporting and Handlers**

```php
error_reporting(E_ALL);

set_exception_handler(function (Throwable $e): void {
    error_log((string) $e);
    http_response_code(500);
});
```

**Files, Streams, and Resource Handles**

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

**Fibers and Cooperative Concurrency**

```php
$fiber = new Fiber(function (): void {
    $value = Fiber::suspend('paused');
    echo $value;
});

$state = $fiber->start();
$fiber->resume('resumed');
```

## Web Input, Output & Security

**Forms, Query Strings, and Validation**

```php
$email = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);

if ($email === false || $email === null) {
    http_response_code(422);
    exit;
}
```

**HTML Output and XSS**

```php
<?= htmlspecialchars(
    $user->displayName,
    ENT_QUOTES | ENT_SUBSTITUTE,
    'UTF-8'
) ?>
```

**Cookies, Sessions, and CSRF**

```php
session_start();
$_SESSION['user_id'] = $userId;

setcookie('theme', 'dark', [
    'secure' => true,
    'httponly' => true,
    'samesite' => 'Lax',
]);
```

**Passwords and Cryptographic APIs**

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

## Databases & External Data

**PDO and Prepared Statements**

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

**JSON and API Payloads**

```php
$data = json_decode($json, true, flags: JSON_THROW_ON_ERROR);

$response = json_encode(
    ['id' => 42, 'name' => 'Mina'],
    JSON_THROW_ON_ERROR,
);
```

## Composer, Autoloading & Architecture

**Namespaces and PSR-4 Autoloading**

```json
{
  "autoload": {
    "psr-4": {
      "App\\": "src/"
    }
  }
}
```

**Composer Dependencies and Lock Files**

```json
{
  "require": {
    "php": "^8.5",
    "psr/log": "^3.0"
  }
}
```

**Dependency Injection and Service Boundaries**

```php
final class ReportService
{
    public function __construct(
        private Clock $clock,
        private ReportRepository $reports,
    ) {}
}
```

## Testing, Analysis & Production

**Unit Testing and PHPUnit**

```php
final class CalculatorTest extends TestCase
{
    public function testAdd(): void
    {
        self::assertSame(5, (new Calculator())->add(2, 3));
    }
}
```

**Static Analysis and Coding Standards**

```php
<?php
/** @return list<User> */
function activeUsers(): array {
    // ...
}
```

**OPcache, Memory, and Performance**

```php
<?php
// Production typically enables OPcache in php.ini.
// Measure application hot paths before manual micro-optimization.
```

**Configuration, Secrets, and Environments**

```php
$dsn = getenv('DATABASE_DSN');
if ($dsn === false) {
    throw new RuntimeException('DATABASE_DSN is required');
}
```
