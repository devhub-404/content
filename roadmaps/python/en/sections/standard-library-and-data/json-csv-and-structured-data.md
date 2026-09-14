# JSON, CSV, and Structured Data

The standard library provides JSON, CSV, TOML reading, XML tools, codecs, and many other data formats. Parsing converts external bytes/text into Python objects but does not prove those objects satisfy your domain schema.

```python
import json

payload = json.loads(text)
name = payload["name"]

encoded = json.dumps({"name": name})
```

Validate untrusted fields, types, ranges, and required keys after parsing or with a schema/model library. Serialization also needs explicit policies for dates, decimals, enums, custom objects, and compatibility across versions.
