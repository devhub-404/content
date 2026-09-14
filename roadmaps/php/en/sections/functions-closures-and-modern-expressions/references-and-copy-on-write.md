# References and Copy-on-write Semantics

PHP values such as arrays use copy-on-write implementation behavior: ordinary assignment behaves like value assignment, while the engine can share storage until mutation requires separation. The reference operator `&` creates aliasing semantics where variables can refer to the same variable container.

```php
$a = [1, 2, 3];
$b = $a;
$b[] = 4;

$c =& $a;
$c[] = 5;
```

Avoid references unless an API specifically needs aliasing or by-reference output/mutation. They can make local reasoning harder because an assignment in one place unexpectedly changes another name.
