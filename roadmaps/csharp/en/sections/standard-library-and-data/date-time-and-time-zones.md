# Date, Time, and Time Zones

`.NET` provides `DateTime`, `DateTimeOffset`, `TimeSpan`, `TimeZoneInfo`, and newer date/time-only types. `DateTimeOffset` represents an instant with an offset and is often safer for timestamps that cross systems, while calendar-only concepts may use `DateOnly`.

```csharp
DateTimeOffset now = DateTimeOffset.UtcNow;
TimeZoneInfo zone = TimeZoneInfo.FindSystemTimeZoneById(
    "America/Los_Angeles");

DateTimeOffset local = TimeZoneInfo.ConvertTime(now, zone);
```

Distinguish instants, local civil times, durations, and dates. Store timestamps in a stable instant representation, convert for display, and use time-zone rules instead of hard-coding offsets because daylight-saving and political changes alter them.
