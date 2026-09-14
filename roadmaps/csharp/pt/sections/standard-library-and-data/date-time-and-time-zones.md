# Data, Hora e Time Zones

.NET fornece `DateTime`, `DateTimeOffset`, `TimeSpan`, `TimeZoneInfo` e tipos date/time-only. `DateTimeOffset` representa instante com offset e costuma ser mais seguro para timestamps entre sistemas, enquanto datas de calendário podem usar `DateOnly`.

```csharp
DateTimeOffset now = DateTimeOffset.UtcNow;
TimeZoneInfo zone = TimeZoneInfo.FindSystemTimeZoneById(
    "America/Los_Angeles");

DateTimeOffset local = TimeZoneInfo.ConvertTime(now, zone);
```

Diferencie instants, local civil time, duration e date. Armazene timestamps em representação estável, converta para display e use regras de time zone em vez de offset hard-coded.
