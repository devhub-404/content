# Client Roots and Hydration

`createRoot` starts a client-rendered React tree in a DOM container. When HTML was already produced by a compatible server render, `hydrateRoot` attaches React behavior to that existing markup instead of throwing it away and rebuilding it from scratch.

```jsx
import { createRoot } from 'react-dom/client';
import App from './App.jsx';

createRoot(document.getElementById('root')).render(<App />);
```

Hydration requires the initial client render to match the server output. Differences caused by random values, time, browser-only branches, or inconsistent data can produce hydration errors. Frameworks normally manage these root APIs for applications and should be preferred when server rendering is required.
