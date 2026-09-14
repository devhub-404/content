# `createMutable` y State Mutation-style

`createMutable` crea un proxy profundamente reactivo cuyas properties pueden asignarse directamente. Puede ser conveniente al integrar código mutation-oriented o cuando la direct property syntax encaja bien con el dominio.

```tsx
const state = createMutable({ count: 0 });

state.count += 1;
```

El modelo de store setter suele ser más auditable porque los updates son explícitos. Usa mutable proxy intencionalmente en vez de mezclar estilos. Pasar un proxy escribible por boundaries amplias puede dificultar ownership y write authority.
