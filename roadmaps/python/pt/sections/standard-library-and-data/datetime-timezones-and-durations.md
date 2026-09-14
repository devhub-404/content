# Datas, Horas, Time Zones e Durations

`datetime` modela date/time/datetime/timedelta e valores aware/naive, enquanto `zoneinfo` fornece regras IANA.

```python
from datetime import datetime, timezone
from zoneinfo import ZoneInfo

now = datetime.now(timezone.utc)
local = now.astimezone(ZoneInfo("America/Los_Angeles"))
```

Diferencie instant de local wall-clock schedule. Armazene timestamps com timezone/UTC e use named zones, não offsets hard-coded. Diferencie sempre instante, data civil, timezone e duração, pois são conceitos parecidos mas não intercambiáveis.
