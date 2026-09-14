# Strings, Bytes, and Text

`str` stores Unicode text, while `bytes` stores immutable byte sequences and `bytearray` mutable bytes. Encoding converts text to bytes under a named character encoding; decoding performs the reverse. Mixing text and binary data without an explicit boundary is an error.

```python
name = "Mina"
message = f"Hello, {name}!"
raw = r"C:\temp\file.txt"

data = "Olá".encode("utf-8")
text = data.decode("utf-8")
```

Use f-strings for ordinary readable interpolation and structured libraries for JSON, HTML, SQL, or shell syntax where escaping rules matter. Always know the encoding at file, network, and process boundaries instead of relying on platform defaults.
