# Custom Exceptions and Error Contracts

Custom exception types are useful when callers need to distinguish a domain failure programmatically rather than parse an error message. Derive from `Exception`, preserve inner exceptions when wrapping, and give the type a stable meaning.

```csharp
public sealed class InvalidOrderException : Exception
{
    public InvalidOrderException(string message)
        : base(message) { }
}
```

Not every validation failure deserves a custom exception. Try-patterns, result types, or ordinary validation collections may be better when failure is expected user flow. Exceptions are strongest when the call cannot produce its promised result normally.
