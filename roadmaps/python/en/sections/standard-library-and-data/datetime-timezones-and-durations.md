# Dates, Times, Time Zones, and Durations

`datetime` models dates, times, datetimes, timedeltas, and timezone-aware or naive values, while `zoneinfo` provides IANA time-zone rules. An aware datetime represents enough offset/time-zone context for many cross-system operations.

```python
from datetime import datetime, timezone
from zoneinfo import ZoneInfo

now = datetime.now(timezone.utc)
local = now.astimezone(ZoneInfo("America/Los_Angeles"))
```

Distinguish an instant from a local wall-clock schedule. Store stable timestamps with timezone/UTC context, convert for display, and use named time zones instead of hard-coded offsets that break under daylight-saving or political changes.
