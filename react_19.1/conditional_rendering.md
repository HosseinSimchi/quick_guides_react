### Conditional Rendering

```javascript
function Item({ name, isPacked }) {
  if (isPacked) {
    return null;
  }
  return <li className="item">{name}</li>;
}
```

### Conditional (ternary) operator (? :)

```javascript
function Item({ name, isPacked }) {
  return (
    <li className="item">{isPacked ? <del>{name + " ✅"}</del> : name}</li>
  );
}
```

### Logical AND operator (&&)

```javascript
return (
  <li className="item">
    {name} {isPacked && "✅"}
  </li>
);
```

### Conditionally assigning JSX to a variable

```javascript
function Item({ name, isPacked }) {
  let itemContent = name;
  if (isPacked) {
    itemContent = <del>{name + " ✅"}</del>;
  }
  return <li className="item">{itemContent}</li>;
}
```
