# Keyframes, easing y reduced motion

`@keyframes` define valores en distintos puntos de una timeline. Las propiedades de animation controlan duración, delay, repeticiones, dirección, fill mode y easing. Curvas Bézier modelan aceleración y `steps()` cambios discretos.

```css
@keyframes pulse {
  0%, 100% { scale: 1; }
  50% { scale: 1.04; }
}

.busy {
  animation: pulse 1.2s ease-in-out infinite;
}

@media (prefers-reduced-motion: reduce) {
  .busy { animation: none; }
}
```

Una animación infinita debería comunicar algo útil, no pedir atención constantemente. `prefers-reduced-motion` permite ofrecer una versión con menos movimiento. Puedes conservar feedback por color u opacity mientras eliminas desplazamientos, zoom o repeticiones intensas.
