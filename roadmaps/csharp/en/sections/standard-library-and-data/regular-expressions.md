# Regular Expressions

`.NET` regular expressions provide pattern matching, capture groups, replacements, options, and advanced constructs. Modern .NET can also generate regex implementations at compile time for known patterns, reducing some runtime parsing and improving trimming/AOT scenarios.

```csharp
var match = Regex.Match(
    "user-42",
    @"^user-(\d+)$");

if (match.Success)
    Console.WriteLine(match.Groups[1].Value);
```

Regex is excellent for lexical text patterns but not automatically the right parser for every structured language. Keep patterns readable, bound untrusted expensive matches with timeouts where appropriate, and use ordinary string methods when the rule is simpler.
