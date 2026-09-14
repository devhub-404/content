# Fecha, Hora y Time Zones

.NET ofrece `DateTime`, `DateTimeOffset`, `TimeSpan`, `TimeZoneInfo` y tipos date/time-only. `DateTimeOffset` representa un instante con offset y suele ser más seguro para timestamps entre sistemas, mientras fechas de calendario pueden usar `DateOnly`.

```csharp
DateTimeOffset now = DateTimeOffset.UtcNow;
TimeZoneInfo zone = TimeZoneInfo.FindSystemTimeZoneById(
    "America/Los_Angeles");

DateTimeOffset local = TimeZoneInfo.ConvertTime(now, zone);
```

Distingue instants, local civil time, duration y date. Guarda timestamps en una representación estable, convierte para display y usa reglas de time zone en vez de offsets hard-coded.
