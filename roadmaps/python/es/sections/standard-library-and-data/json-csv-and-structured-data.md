# JSON, CSV y Datos Estructurados

La standard library ofrece JSON, CSV, TOML, XML y otros formatos. Parsing convierte bytes/text en objects, pero no demuestra el schema del dominio.

```python
import json

payload = json.loads(text)
name = payload["name"]

encoded = json.dumps({"name": name})
```

Valida fields, types, ranges y keys después del parsing o con una schema library. La serialización necesita políticas para dates, decimal, enums y versionado.
