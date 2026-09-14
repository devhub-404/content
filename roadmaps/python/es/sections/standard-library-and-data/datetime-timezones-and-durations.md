# Fechas, Horas, Time Zones y Durations

`datetime` modela date/time/datetime/timedelta y valores aware/naive, mientras `zoneinfo` ofrece reglas IANA.

```python
from datetime import datetime, timezone
from zoneinfo import ZoneInfo

now = datetime.now(timezone.utc)
local = now.astimezone(ZoneInfo("America/Los_Angeles"))
```

Distingue un instant de un local wall-clock schedule. Guarda timestamps con timezone/UTC y usa named zones, no offsets hard-coded. Distingue siempre instante, fecha civil, timezone y duración, porque son conceptos parecidos pero no intercambiables.
