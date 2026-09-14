# Passwords and Cryptographic APIs

PHP provides high-level password hashing and verification APIs that select secure password schemes and encode required parameters in the stored hash. General cryptographic primitives are also available through dedicated extensions and functions.

```php
$hash = password_hash($password, PASSWORD_DEFAULT);

if (!password_verify($candidate, $hash)) {
    throw new AuthenticationException();
}
```

Never store plaintext passwords or invent your own password hashing scheme. Use `random_bytes`/`random_int` for security-sensitive randomness and established libraries/protocols for encryption, signing, key derivation, and token handling.
