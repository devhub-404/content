# Client Roots e Hydration

`createRoot` inicia React tree client-rendered em um DOM container. Quando HTML já veio de server render compatível, `hydrateRoot` conecta comportamento React ao markup existente em vez de descartá-lo e reconstruir tudo.

```jsx
import { createRoot } from 'react-dom/client';
import App from './App.jsx';

createRoot(document.getElementById('root')).render(<App />);
```

Hydration exige que o primeiro client render corresponda ao server output. Diferenças por random, time, branches browser-only ou dados inconsistentes causam errors. Frameworks normalmente gerenciam roots e devem ser preferidos para server rendering.
