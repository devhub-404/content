# Tipos de Pacote e Export Maps

Pacote publicado precisa alinhar entry points JavaScript e entry points de tipos. Export maps modernos podem expor subpaths e conditions diferentes, e o module resolver do TypeScript usa esse metadata conforme ambiente configurado.

```ts
{
  "name": "example-lib",
  "type": "module",
  "exports": {
    ".": {
      "types": "./dist/index.d.ts",
      "import": "./dist/index.js"
    }
  }
}
```

Não publique declarations para paths que consumidores não conseguem importar em runtime, nem runtime paths sem tipos correspondentes quando biblioteca promete suporte tipado. Teste artefato empacotado/publicado a partir de pequeno projeto consumidor. Aliases locais de source podem esconder erros de packaging que aparecem apenas após instalação.
