### Exporting and importing a component

###### Gallery.js

```javascript
export default function Gallery() {
  return (
    <section>
      <h1>Amazing scientists</h1>
    </section>
  );
}
```

###### App.js

```javascript
import Gallery from "./Gallery.js";

export default function App() {
  return <Gallery />;
}
```
