# Layers, scope y `!important`

Cascade layers crean grupos explícitos de precedencia. En declaraciones normales de autor, una layer posterior vence a una anterior sin importar la especificidad. Las declaraciones `!important` invierten la prioridad entre layers, por lo que las layers son una herramienta de arquitectura, no solo de organización visual.

```css
@layer reset, base, components, utilities;

@layer components {
  .button { padding: .6rem 1rem; }
}

@layer utilities {
  .p-0 { padding: 0; }
}

@scope (.article) {
  a { color: #2457d6; }
}
```

`@scope` limita reglas a una región del DOM y añade proximidad de scope como desempate tardío. `!important` no significa «máxima especificidad»: cambia la prioridad de la cascada y debe reservarse para contratos deliberados. Mezcla CSS con y sin layer de forma consciente porque el CSS normal no-layered tiene prioridad sobre el normal layered.
