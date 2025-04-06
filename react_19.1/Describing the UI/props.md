### Pass props to the child component

###### Profile.js

```javascript
export default function Profile() {
  return (
    <Avatar person={{ name: "Lin Lanying", imageId: "1bX5QH6" }} size={100} />
  );
}
```

###### Avatar.js

```javascript
function Avatar({ person, size }) {
  // person and size are available here
}
```

### Pass props to the child component

```javascript
function Avatar({ person, size = 100 }) {
  // ...
}
```

### Forwarding props with the JSX spread syntax

```javascript
function Profile({ person, size, isSepia, thickBorder }) {
  return (
    <div className="card">
      <Avatar
        person={person}
        size={size}
        isSepia={isSepia}
        thickBorder={thickBorder}
      />
    </div>
  );
}
```

```javascript
function Profile(props) {
  return (
    <div className="card">
      <Avatar {...props} />
    </div>
  );
}
```

### Passing JSX as children

```javascript
export default function Profile() {
  return (
    <Card>
      <Avatar
        size={100}
        person={{
          name: "Katsuko Saruhashi",
          imageId: "YfeOqp2",
        }}
      />
    </Card>
  );
}
```

```javascript
function Card({ children }) {
  return <div className="card">{children}</div>;
}
```
