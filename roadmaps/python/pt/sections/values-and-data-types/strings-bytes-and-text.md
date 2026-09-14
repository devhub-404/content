# Strings, Bytes e Texto

`str` armazena Unicode text, `bytes` sequência imutável de bytes e `bytearray` bytes mutáveis. Encoding converte texto em bytes e decoding faz o inverso.

```python
name = "Mina"
message = f"Hello, {name}!"
raw = r"C:\temp\file.txt"

data = "Olá".encode("utf-8")
text = data.decode("utf-8")
```

Use f-strings para interpolation comum e libraries estruturadas para JSON, HTML, SQL ou shell. Conheça o encoding nas boundaries de file/network/process.
