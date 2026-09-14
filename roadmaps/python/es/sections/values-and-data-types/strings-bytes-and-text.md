# Strings, Bytes y Texto

`str` almacena texto Unicode, `bytes` una secuencia inmutable de bytes y `bytearray` bytes mutables. Encoding convierte texto a bytes y decoding hace lo contrario.

```python
name = "Mina"
message = f"Hello, {name}!"
raw = r"C:\temp\file.txt"

data = "Olá".encode("utf-8")
text = data.decode("utf-8")
```

Usa f-strings para interpolación normal y libraries estructuradas para JSON, HTML, SQL o shell. Conoce el encoding en boundaries de file/network/process.
