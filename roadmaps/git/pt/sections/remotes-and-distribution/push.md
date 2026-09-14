# Fazer Push de Refs com Segurança

Push envia objetos ausentes e solicita atualização de refs remotas. Push normal é rejeitado quando descartaria histórico remoto conforme as regras, protegendo trabalho adicionado desde seu último estado conhecido.

```bash
git push -u origin feature/login
git push origin main
git push --force-with-lease
```

Se reescrita for intencional, prefira `--force-with-lease` a `--force`: o lease verifica se a ref remota ainda corresponde ao estado esperado. Branches protegidas podem recusar reescrita de qualquer forma.
