# HTML Output and XSS

Cross-site scripting occurs when untrusted data becomes executable markup or script in a page. HTML text, HTML attributes, JavaScript, CSS, and URLs are different output contexts and need appropriate encoding or safe templating rules.

```php
<?= htmlspecialchars(
    $user->displayName,
    ENT_QUOTES | ENT_SUBSTITUTE,
    'UTF-8'
) ?>
```

Prefer template engines and framework helpers with context-aware auto-escaping. Do not “sanitize once” and then reuse data in every context; keep the original value and encode at the output boundary for its exact destination.
