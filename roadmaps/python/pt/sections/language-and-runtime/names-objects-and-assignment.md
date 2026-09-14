# Nomes, Objetos e Assignment

Variáveis Python são nomes ligados a objetos; assignment não copia objeto por default. Dois nomes podem apontar ao mesmo objeto mutável, então mutation por um alias aparece no outro.

```python
items = [1, 2, 3]
alias = items
alias.append(4)

print(items)  # [1, 2, 3, 4]
```

Raciocine sobre identidade, mutability e ownership conventions em vez de imaginar boxes independentes. Copie apenas quando estado independente é necessário e saiba se a cópia é shallow ou deep.
