# Nombres, Objetos y Assignment

Las variables Python son nombres ligados a objetos; assignment no copia un objeto por defecto. Dos nombres pueden referirse al mismo objeto mutable, por lo que una mutation mediante un alias se ve desde el otro.

```python
items = [1, 2, 3]
alias = items
alias.append(4)

print(items)  # [1, 2, 3, 4]
```

Razona sobre identidad, mutability y ownership conventions en vez de imaginar cajas independientes. Copia solo cuando necesites estado independiente y sabe si la copia es shallow o deep.
