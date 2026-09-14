# Client Roots y Hydration

`createRoot` inicia un React tree client-rendered en un DOM container. Cuando el HTML ya proviene de un server render compatible, `hydrateRoot` conecta comportamiento React al markup existente en vez de descartarlo y reconstruir todo.

```jsx
import { createRoot } from 'react-dom/client';
import App from './App.jsx';

createRoot(document.getElementById('root')).render(<App />);
```

Hydration exige que el primer client render coincida con el server output. Diferencias por random, time, branches browser-only o datos inconsistentes causan errors. Los frameworks normalmente gestionan roots y deberían preferirse para server rendering.
