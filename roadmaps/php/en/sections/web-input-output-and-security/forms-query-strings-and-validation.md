# Forms, Query Strings, and Validation

Web input arrives as strings, arrays, uploaded files, headers, cookies, and server metadata. Filtering helpers can validate selected scalar formats, but application rules still require explicit validation and normalization.

```php
$email = filter_input(INPUT_POST, 'email', FILTER_VALIDATE_EMAIL);

if ($email === false || $email === null) {
    http_response_code(422);
    exit;
}
```

Validate at the boundary, convert to domain types, and reject unexpected shapes early. Do not treat a value as safe merely because it came from a hidden form field, cookie, session, or browser-generated control.
