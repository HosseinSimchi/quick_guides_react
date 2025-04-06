### React assumes that every component you write is a pure function. This means that React components you write must always return the same JSX given the same inputs

```javascript
function double(number) {
  return 2 * number;
}
```

_In the above example, double is a pure function. If you pass it 3, it will return 6. Always._

### React’s rendering process must always be pure. Components should only return their JSX, and not change any objects or variables that existed before rendering—that would make them impure!

```javascript
function Cup() {
  // Bad: changing a preexisting variable!
  guest = guest + 1;
  return <h2>Tea cup for guest #{guest}</h2>;
}
```

_This component is reading and writing a guest variable declared outside of it. This means that calling this component multiple times will produce different JSX!_

_You can fix this component by passing guest as a prop instead:_

```javascript
function Cup({ guest }) {
  return <h2>Tea cup for guest #{guest}</h2>;
}

export default function TeaSet() {
  return (
    <>
      <Cup guest={1} />
      <Cup guest={2} />
      <Cup guest={3} />
    </>
  );
}
```
