### Passing strings with quotes

```javascript
export default function Avatar() {
  const avatar = "https://i.imgur.com/7vQD0fPs.jpg";
  const description = "Gregorio Y. Zara";

  return <img className="avatar" src={avatar} alt={description} />;
}
```

### Using “double curlies”: CSS and other objects in JSX

```javascript
export default function TodoList() {
  return (
    <ul
      style={{
        backgroundColor: "black",
        color: "pink",
      }}
    >
      <li>Improve the videophone</li>
    </ul>
  );
}
```
