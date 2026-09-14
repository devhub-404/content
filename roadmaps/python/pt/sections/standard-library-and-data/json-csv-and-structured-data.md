# JSON, CSV e Dados Estruturados

Standard library fornece JSON, CSV, TOML, XML e outros formatos. Parsing converte bytes/text em objects, mas não prova schema do domínio.

```python
import json

payload = json.loads(text)
name = payload["name"]

encoded = json.dumps({"name": name})
```

Valide fields, types, ranges e keys depois do parsing ou com schema library. Serialization precisa políticas para dates, decimal, enums e versioning.
